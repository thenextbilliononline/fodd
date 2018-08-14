---
title: DisasterRadio SDR software
permalink: /DisasterRadio/SDR_software/
---

This page is currently a bit of a mess, containing only some notes about GNU Radio. Much documentation work needed.

Source code
===========

The code is [available on github](https://github.com/DisasterRadio/DisasterRadioSDR).

Interesting links
=================

-   [List of awesome GNU Radio projects](https://www.cgran.org/wiki/Projects)

UHD gain selection
==================

The command:

` sudo uhd_find_devices`

Should list the gain range for the TX or RX frontend of choice.

E.g. for the WBX TX frontend you get:

` Gain range PGA0: 0.0 to 25.0 step 0.1 dB`

Make sure you're not looking at the gain range for TX when you're looking to receive or vice-versa, as the won't necessarily be the same!

GNU Radio UHD device selection
==============================

For a USRP 1 this should be in the form: serial=<hex_serial>. E.g:

` serial=24e6b31a`

To find device serial run:

` sudo uhd_find_devices`

You're looking for output that looks like:

`|     _____________________________________________________`
`|    /`
`|   |       Mboard: USRP1`
`|   |   serial: 24e6b31a`

To set the sub-device (the daughterboard and channel) use the format:

` `<slot_name>`:`<daughterboard_frontend_id>

E.g:

` B:0`

This slot_name and daughterboard_frontend_id are also findable with the command:

` sudo uhd_find_devices`

The output you're looking for looks like:

`|   |     _____________________________________________________`
`|   |    /`
`|   |   |       RX Dboard: B`
`|   |   |   ID: WBX, WBX + Simple GDB (0x0053)`
`|   |   |     _____________________________________________________`
`|   |   |    /`
`|   |   |   |       RX Frontend: 0`
`|   |   |   |   Name: WBXv2 RX+GDB`
`|   |   |   |   Antennas: TX/RX, RX2, CAL`
`|   |   |   |   Sensors: lo_locked`
`|   |   |   |   Freq range: 68.750 to 2200.000 Mhz`
`|   |   |   |   Gain range PGA0: 0.0 to 31.5 step 0.5 dB`
`|   |   |   |   Connection Type: IQ`
`|   |   |   |   Uses LO offset: No`

Specifically the lines:

`|   |   |       RX Dboard: B`

and:

`|   |   |   |       RX Frontend: 0`

Together making up the B:0.

For command-line python scripts
-------------------------------

For command line scripts, device and sub-device is often specified with the --args and --spec arguments. E.g:

` my_script.py --args serial=24e6b31a --spec B:0`

This syntax may vary from script to script, but this is the most common syntax.

For GNU Radio Companion
-----------------------

For the “UHD: USRP Sink” in the latest version of grc (as of this writing) the field “Device Addr” would be set to e.g. serial=24e6b31a and the field “Mb0: Subdev Spec” would be set to e.g. “B:0”.

[Category:Proposed Projects](/Category:Proposed_Projects "wikilink") [Category:Stub](/Category:Stub "wikilink") [Category:DisasterRadio](/Category:DisasterRadio "wikilink")