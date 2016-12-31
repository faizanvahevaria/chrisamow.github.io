---
layout: post
title: "gae sqlalchemy gaps"
category: 
tags: []
comments: true
---
{% include JB/setup %}
Some notes for running sqlalchemy on app engine / cloud sql - things missing from the [direct MySQLdb documentation](https://cloud.google.com/appengine/docs/python/cloud-sql/) or slight inaccuracies.  There have been many changes over the last few years so stackoverflow has a lot of outdated info.
  
I like the proxy option so you can check the actual connection strings.  I used the unix sockets option, all the examples show that option being used so I haven't tried the tcp sockets
  
  
## service account
You need to make a [service account](https://cloud.google.com/sql/docs/sql-proxy#authentication-options)  <https://console.cloud.google.com/iam-admin/serviceaccounts/project?project=hijo-154008>
  
The directions there are good, so I moved the .json file to the app directory and it works:

	./cloud_sql_proxy -dir=/cloudsql -credential_file=hijo-87ed1817fd6d.json -instances=hijo-154008:us-central1:hijodb &
   
   
## connection string

[sqlalchemy docs](http://docs.sqlalchemy.org/en/latest/dialects/mysql.html?highlight=appengine#module-sqlalchemy.dialects.mysql.mysqldb) say the connection string needs to be:
mysql+mysqldb://root@/<dbname>?unix_socket=/cloudsql/\<projectid\>:\<instancename\>

So my setup looks like this:
projectid: hijo-154008
instancename: hijodb

When I run the ./cloud_sql_proxy it says:

	2016/12/31 02:09:25 Listening on /cloudsql/hijo-154008:us-central1:hijodb for hijo-154008:us-central1:hijodb

so you can see the extra regional info in there ":us-central1", as a reminder you can get that from:

	➜  urling  ★ gcloud sql instances describe hijodb
	connectionName: hijo-154008:us-central1:hijodb
  
  
## enabling cloud sql api

you will see this:

	2016/12/31 02:13:12 New connection for "hijo-154008:us-central1:hijodb"
	2016/12/31 02:13:13 couldn't connect to "hijo-154008:us-central1:hijodb": ensure that the account has access to "hijo-154008:us-central1:hijodb" (and make sure there's no typo in that name). Error during createEphemeral for hijo-154008:us-central1:hijodb: googleapi: Error 403: Access Not Configured. Cloud SQL Administration API has not been used in project 623765949728 before or it is disabled. Enable it by visiting https://console.developers.google.com/apis/api/sqladmin/overview?project=623765949728 then retry. If you enabled this API recently, wait a few minutes for the action to propagate to our systems and retry., accessNotConfigured

and yes!  there is a triangle blue Enable button to click and after a few minutes it does work


## don't forget to create the db
  
(making sure it matches the dbname from the connection string)
  
<https://console.cloud.google.com/sql/instances/hijodb/databases?project=hijo-154008>
  
  
## db dialects
  
for example with mysql, if you use a String it must have a length String(100), otherwise you'll get:

	CompileError: (in table 'users', column 'name'): VARCHAR requires a length on dialect mysql


