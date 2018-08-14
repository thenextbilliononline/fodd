---
title: Beagle Bone Black
permalink: /Beagle_Bone_Black/
---

See Also: [Mesh/Hardware Fourth Milestone](/Mesh/Hardware_support#Fourth_milestone "wikilink")

notes about BBB - Beagle Bone Black

OS Install
----------

### OpenWRT

-   <https://github.com/artekw/openwrt-bbb>

### Adafruit tutorial

<https://learn.adafruit.com/beaglebone-black-installing-operating-systems/angstrom>

first light
-----------

Just booting up...

### using an FTDI device plugged into J1 pins

find the serial port for the FTDI USB adapter

`ls /dev/tty*`

-   might be /dev/ttyAMA0 on linux
-   might be /dev/tty.usbmodemfa133 on mac

Wiring from the FTDI device:

-   BBB - FTDI
-   pin 1 GND - GND
-   pin 4 RX - TX
-   pin 5 TX - RX

in terminal:

`screen `<usbdevicename>` 115200`

-   first login with root, no password

**Mesh the planet...**

Configuring B.A.T.M.A.N to Mesh with Sudo Mesh
==============================================

This tutorial assumes that you have your Beagle Bone configured running Debian Wheezy. It is all recommended that you disabel network-manager.

Add batman module to the kernel

    modprobe batman-adv

Add B.A.T.M.A.N interface

    batctl if add eth0

Disable Wifi

    ifconfig wlan0 down

Set MTU

    ifconfig wlan0 mtu 1532

Turn on Ad-Hoc Mode and connect to the SSID ppslopen.net-node2node with the Mac Address CA:FE:C0:DE:F0:0D on Channel 11

    iwconfig wlan0 mode ad-hoc essid pplsopen.net-node2node ap CA:FE:C0:DE:F0:0D channel 11

Connect B.A.T.M.A.N interface to Wlan

    batctl if add wlan0

Turn on wlan0 and bat0 interfaces

    ifconfig wlan0 up
    ifconfig bat0 up

Connect to your network. Subject to change depending on our network's subnet

    ifconfig bat0 10.200.8.1
    route add default gw 10.0.99.1

Enable Port Forwarding

    echo 1 > /proc/sys/net/ipv4/ip_forward