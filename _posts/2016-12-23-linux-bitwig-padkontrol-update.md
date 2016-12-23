---
layout: post
title: "linux bitwig padkontrol update"
category: makemusic
tags: [padkontrol, bitwig]
comments: true
---
{% include JB/setup %}
  
I've seen many variations of instructions out there which partially work, so I'll leave notes on what worked for me.
  
GOAL: get audio working simultaneously from bitwig and the rest of the apps (so you can play along to youtube songs to drum along for example)
  
note that it may be intuitively tempting to skip jack and just use alsa since it has supported mixing for a while: 1. my usb sound interface always goes into distortion mode eventually (within a half hour of playing or if you go in/out of suspend mode; 2. I think you have to hardcode configure the various apps to do the mixing

```
#installation for jack and the bridge from pulseaudio to jack
sudo apt-get install jack-tools ant openjdk-6-jdk fftw3 qjackctl
sudo apt-get install pulseaudio-module-jack pavucontrol
```
  
I did not have success with qjackctl - it did not even have the device listing below where it should have.  But a lot of people do swear by it.
  
  
```
#figure out your soundcard name (between the brackets)
➜  ~  ★ cat /proc/asound/cards
  0 [MID            ]: HDA-Intel - HDA Intel MID
                       HDA Intel MID at 0xf6ffc000 irq 43
  1 [padKONTROL     ]: USB-Audio - padKONTROL
                       KORG INC. padKONTROL at usb-0000:00:1d.0-1.2, full speed


#make sure you arent running programs using alsa and start the jack daemon
jackd -dalsa -dhw:MID &		#for my scarlett solo it was -dhw:USB

#enable the pulse audio to jack bridge - many apps just want pulseaudio
pacmd load-module module-jack-source channels=2; pacmd load-module module-jack-sink channels=2;


pavucontrol &
#then set the apps to use the pulseaudio-alsa
```


GOAL: get the padkontrol to work on bitwig
  
As noted by others, the built-in script for padkontrol does not seem to work at all, but the generic one does.
    
What I've found is that if you start with the generic one you can then do an auto detect and it finds the padkontrol and sets it up!  (In the control script console you'll see the init() and exit() called for the generic script.)  Something is still not quite right, the padkontrol status says "drN" and the Assign light/mode for control knob 2 is locked on.  The good thing is that the pads are mapped to C1 to D#2 (lower left to upper right) so you don't have to remap them every time you plug in - which is the biggest usability problem since the padkontrol doesn't have persistent onboard storage.  The worst problem is that because it is locked in some funny mode you can't change the velocity curves and can't do scene changes.
  
When I know more and am sure it is repeatable I'll post on some of the sites where people are posting problems.

