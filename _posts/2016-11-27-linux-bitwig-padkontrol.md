---
layout: post
title: "linux bitwig padkontrol"
category: makemusic
tags: [daw]
comments: true
---
{% include JB/setup %}
  
I am expecting this to be a work in progress, but at least it is somewhat working...
  
On linux bitwig 1.3.5, the korg padkontrol control script is missing some lines from the official <https://github.com/bitwig/korg-padkontrol/>
  
	➜  korg-padkontrol git:(master) ★ diff padKONTROL.control.js /opt/bitwig-studio/resources/controllers/korg/padKONTROL.control.js
	6,8d5
	< host.addDeviceNameBasedDiscoveryPair(["padKONTROL", "MIDIIN3 (padKONTROL)"], ["MIDIOUT2 (padKONTROL)"]);
	< host.addDeviceNameBasedDiscoveryPair(["padKONTROL MIDI 1", "padKONTROL MIDI 3"], ["padKONTROL MIDI 2"]);
	<
	426c423
  
Nevertheless, neither of them work.  
The only thing that does work is adding it manually as a Generic MIDI Keyboard and setting the top midi in setting to padKontrol MIDI 2
  
Unfortunately, the console (View / Show Control Script Console) doesn't reveal anything in either case.  It actually crashed on me one time.  And doing a restart there seems to cause the program to terminate instead of doing a controllers reinit.
  
Hopefully I find a way to get more debug info.  I am posting this partly because some people think that padkontrol doesn't work with bitwig at all, but at least I can use the pads and xy controller now, without the 2 midi knob controllers.  I'm surprised the roll and flam functionality doesn't seem to work - I thought that would be on device generated midi.
  
Just remember that the padkontrol C2 will trigger C1 on bitwig (everything is an octave lower).  At least it's nice that you don't need any drivers on linux with alsa built-in support.
(even though it doesn't seem to show when doing a "aplaymidi -l" )
