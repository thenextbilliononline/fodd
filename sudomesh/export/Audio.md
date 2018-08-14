---
title: Audio
permalink: /Audio/
---

*To stream audio in the space, see [music](/music "wikilink")*'

Audio Production Equipment
==========================

Drums
-----

We have a drum kit stored in the top of the recording studio

Bass guitar
-----------

Bass guitar ready to rock in the recording studio

guitar
------

Guitar in the recording studio

Microphones
-----------

There is a [Blue Icicle](http://bluemic.com/icicle/) **USB microphone** (Inventory [ID 16](http://space.local/view/16)) in the audio production closet.

FYI Some audio programs such as [Audacity](http://audacity.sourceforge.net/) require plugging in the microphone before starting the program[1](http://forum.audacityteam.org/viewtopic.php?f=13&t=32759).

Amplifier and speakers
======================

**You can play [music from the file server](/Music "wikilink") while inside the space**

The amplifier and speakers were donated by Jehan.

The amp is hooked up to the laptop on the shelf, which is the space server. Its hostname is hairball.local (using zeroconf, which should be default enabled on most gnu/linux and OS X machines, but not on windows).

The space server is running a pulseaudio server which is announced using zeroconfig.

Streaming audio to the space server
-----------------------------------

In order to stream audio from your computer to space.local, you need to have pulseaudio installed. This is default in Ubuntu. You also need some way of switching between local sound output and network sound output.

### Command line method

'''warning: ''' this hasn't been tested

Open a new terminal and do:

` export PULSE_SERVER=tcp:space.local:4713`

Anything you play from applications launched from that terminal should then play through the space audio server.

### GUI method

Check if padevchooser is available for your system:

` apt-cache search padevchooser`

If it is, then install it:

` sudo aptitude install padevchooser`

If not (it's not available on newer Ubuntu systems), then you can use pasystray. You need to add this PPA:

` sudo add-apt-repository ppa:christoph-gysin/pasystray`
` sudo aptitude update`
` sudo aptitude install pasystray`

If you're using Unity (default in Ubuntu) allow systray icons from all applications (since Unity blocks them):

` gsettings set com.canonical.Unity.Panel systray-whitelist `“`['all']`”

Now reload unity:

` unity --replace & `

Start padevchooser or pasystray.

A system tray icon should appear in the top right corner. Click it and choose pulse@hairball as the default server, then as default sink, choose the option called something like “pulse@hairball: Buil-in Audio Analog Stereo”.

Start some program that plays audio (if the program was already running you may have to restart it after changing sinks).

The audio should play out of the sudo room sound system speakers.

[Category:Projects](/Category:Projects "wikilink")

[Category:Music](/Category:Music "wikilink")