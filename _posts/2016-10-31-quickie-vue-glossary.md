---
layout: post
title: "quickie vue glossary"
category: vue
tags: [vue, glossary]
---
  
Generating this from a list for convenience, not beauty - will be a living doc.  in my words, so [maybe](https://www.youtube.com/watch?v=G2y8Sx4B2Sk)
  
---

ajax example : simple example using axios and lodash  <http://vuejs.org/guide/computed.html#Watchers>   Note: vue-resource provides ajax functionality

auto prefixing : When you use a CSS property that requires vendor prefixes in ```v-bind:style```, for example ```transform```, Vue will automatically detect and add appropriate prefixes to the applied styles

beginner gotchas : <https://vuejs.org/2016/02/06/common-gotchas/>

comparison : <https://v1.vuejs.org/guide/comparison.html>

component caching : components will only be rerendered if the state upon which they are based has been mutated

component : in vue, a [component](http://vuejs.org/guide/components.html) is a vue instance representing a custom html element with pre-defined options.  Registering a component in Vue is [straightforward](http://vuejs.org/guide/index.html#Composing-with-Components)  

computed getter/setter : read and write vue data without side effects

computed property : user vue function to expose transformed access to vue data.  note the missing parentheses.  The difference (since it will work as a normal function with the parens) is that the computed properties are cached based on their dependencies

curated awesome things : <https://github.com/vuejs/awesome-vue>

custom elements : part of the Web Components Spec - vue components are loosely modeled after the spec, but with key differences

declarative rendering : [you specify what you want, the system figures out how to achieve it.  declarative allows projections](https://twitter.com/dan_abramov/status/789198570129805312)

directive : prefixed with v- (special attributes provided by vue applying special reactive behavior to the rendered DOM)  It is expected to be a single javascript expresion, with the exception of v-for

ecosystem : [vue.js ecosystem](https://v1.vuejs.org/guide/application.html),  [list](https://github.com/vuejs/awesome-vue#user-content-development-tools)

event modifiers : v-on abstraction for stop, prevent, capture, self - think event.preventDefault() or event.stopPropagation()

examples : [hackernews clone](https://github.com/vuejs/vue-hackernews)

interpolation - evaluation of string result after filling in placeholders

jsx : a declarative XML-like syntax that works within Javascript. vue supports jsx via the Babel plugin 

key modifiers : v-on [keyboard monitoring](http://vuejs.org/guide/events.html#Key-Modifiers) 

key : To give Vue a hint so that it can track each node’s identity, and thus reuse and reorder existing elements, you need to provide a unique key attribute for each item. An ideal value for key would be the unique id of each item

lifecycle diagram : <http://vuejs.org/guide/instance.html#Lifecycle-Diagram>

lifecycle hooks : enable custom functionality at important parts of the vue lifecycle.  Including: mounted, updated, destroyed.  In vue there are no controllers, custom logic for a component would go in the lifecycle hooks.  See lifecycle diagram

mutation methods : for array change detection: push, pop, shift, unshift, splice, sort, reverse. The following are undetectable: directly setting with index, modifying .length.  Computed properties should be used for sorting and filtering

mvvm : design pattern - vue design does not exactly match it, but it was inspired by it

progressive framework : A view layer only core library with incrementally adoptable ecosystem of supporting libraries

proxies : vue instance proxies all properties found in its data object e.g. vm.a === data.a // -> true  It should be noted that only these proxied properties are reactive. If you attach a new property to the instance after it has been created, it will not trigger any view updates

reactive : structured data flow with specific limited methods of mutation that facilitates robust handling of complicated async data streams.  conceptually related to functional programming

render function : direct generation of html for cases where the templates are not well suited

server side rendering : with some [extra steps](https://vuejs.org/guide/ssr.html), the vue app can have the web server emit the page html so seo and other static page benefits can still work

symbol dollar : In addition to data properties, Vue instances expose a number of useful instance properties and methods. These properties and methods are prefixed with $ to differentiate them from proxied data properties

symbol double mustaches : data is plain text, not html

template : all vue templates are spec compliant [valid html](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template). they are converted into DOM render functions. Combined with the reactivity system, Vue is able to intelligently figure out the minimal amount of components to re-render and apply the minimal amount of DOM manipulations when the app state changes

virtual dom : a parallel representation of the DOM optimized so that final rendering is fast and efficient

vue-cli : scaffolding for quick battery included project start [usage](https://vuejs.org/2015/12/28/vue-cli/)  use it with the [vuejs-templates](https://github.com/vuejs-templates)

v-bind : directive ```<a v-bind:href="url"></a>``` (shorthand) ```<a :href="url"></a>```.  Mustaches cannot be used inside HTML attributes, instead use a v-bind directive  ```v-bind:id="dynamicId"```.  It also works for boolean attributes - the attribute will be removed if the condition evaluates to a falsy value:```v-bind:disabled="someDynamicCondition"```   e.g. keep this elements title attribute up-to-date with the message property of on the vue instance.  there are [special enhancements for class and style and arrays](http://vuejs.org/guide/class-and-style.html)

v-else : can only be used immediately following v-if

v-for : directive used for displaying [list rendering](http://vuejs.org/guide/list.html) using the data from an array.  Templates are supported like v-if. Properties can also be iterated. An integer can be used to repeat templates.  You can directly use v-for on a custom component, like any normal element. It is recommended to provide a key with v-for whenever possible, unless the iterated DOM content is simple, or you are intentionally relying on the default behavior for performance gains

v-html : data contents are plain html, data bindings are ignored.  Note that you cannot use v-html to compose template partials, because Vue is not a string-based templating engine. Instead, components are preferred as the fundamental unit for UI reuse and composition.  Dynamically rendering arbitrary HTML on your website can be very dangerous because it can easily lead to XSS attacks. Only use HTML interpolation on trusted content and never on user-provided content.

v-if : Here, the v-if directive would remove/insert the element based on the truthiness of the value of the expression seen.  [Template elements can be used to wrap multiple elements](http://vuejs.org/guide/conditional.html)

v-model : directive for two-way binding between form input (text area elements, checkboxes, radiobuttons, dropdown selects) and app state.  Modifiers include: lazy, number, trim

v-once : directive for one-time interpolations that do not update on a data change

v-on : directive ```<a v-on:click="doSomething"></a>``` (shorthand) ```<a @click="doSomething"></a>``` attaches event listeners that invoke methods on vue instance.  Inline calls with params can be used

v-show : always render and remain in the DOM. Prefer it to v-if if toggled often

watched property : [generic way to observe and react to data changes](http://vuejs.org/guide/computed.html#Computed-vs-Watched-Property), often computed properties should be used instead

weex : "react native for vue" - [cross platform framework](http://alibaba.github.io/weex/) officially powered by vue by a large chinese ecommerce company

zero config time travel : the chrome vue extension supports [time travel](https://onsen.io/blog/content/images/2016/Jun/react_redux_devtools_time_travel.gif) as is.  It lets you replay actions/mutations and export them for developer collaboration

<!--  easiest way to use this for each definition, add at the top a (possibly long) single line entry with md embedded.  For double spaced results, (sort, remove blank lines, double space) sort -V -f -t":" unsorted-vue-glossary.md | awk 'NF' | sed G > vue-glossary-sorted.md; grip vue-glossary-sorted.md    Unfinished terms can be found looking for ":  "    -->

