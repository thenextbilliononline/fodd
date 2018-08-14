---
title: DisasterRadio Android app
permalink: /DisasterRadio/Android_app/
---

The Android app should at minimum contain a browsable offline map of the local area that displays locations of various emergency-relevant services. It should include automatic bluetooth synchronization to receive stations and other phones.

The code is [available on github](https://github.com/DisasterRadio/DisasterRadioAndroid).

Bluetooth
=========

The bluetooth device discovery and connection from Android phones is working, but we're having trouble connecting to python-bluez examples and currently troubleshooting. Could be because python-bluez is unmaintained since 2009 or because the bluetooth usb sticks we have just plain suck.

Interesting projects:

-   [Blue-Mesh](https://github.com/schnej7/Blue-Mesh)

Synchronization
===============

We'll use a variation on [scuttlebutt](https://github.com/dominictarr/scuttlebutt) synchronization that supports receive-only “sync”. Currently porting to Java.

Maps
====

There seem to be two Android map libraries:

-   [MapsForge](http://code.google.com/p/mapsforge/) - Vector-based


Seems like development stopped in late 2012. Map download server is down. I tried it out and while it's pretty fast even on an older phone, the map is not impressive to look at.

-   [osmdroid](http://code.google.com/p/osmdroid/) - Bitmap-based

[Category:Proposed Projects](/Category:Proposed_Projects "wikilink") [Category:DisasterRadio](/Category:DisasterRadio "wikilink")