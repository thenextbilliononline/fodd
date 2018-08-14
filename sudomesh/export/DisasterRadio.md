---
title: DisasterRadio
permalink: /DisasterRadio/
---

<center>
[600px](/File:Disasterradio_banner_with_subtitle_icon_sunflip.png "wikilink")

</center>
Introduction
============

DisasterRadio is an off-grid (solar-powered) low-bandwidth long-range mesh network built on free and open source software and affordable open hardware.

The nodes are small and entirely self-contained units that can be deployed simply by leaving them in a place with sun. They are intended for either manual or drone-deployment on rooftops or in windows. They use high gain omni-directional antennas on 915 MHz using the LoRa PHY (Chirp Spread Spectrum) to talk to each-other and a downward-pointing/inward-pointing high gain wifi antenna to talk to user devices (phones/tables/laptops) inside the buildings on which they are placed. They use a low-power microcontroller running a web server that lets anyone use the network as long as they have a device with wifi and a web-browser.

Updates
=======

-   Status as of 31 October 2017: [User:nanomonkey](/User:nanomonkey "wikilink") and fritz received the custom PCB boards they designed. got one working tonight \\o/
-   Status as of June 10th 2017: Basic chat between two nodes working. A more fleshed-out website should appear here soon.

Applications
============

The in-development apps are secure chat and community resource mapping (an offline map that communities can use to add resources, like [tidepools](http://tidepools.co/)).

Technical Specifications
========================

-   Bandwidth: &lt; 2000 kbits/sec.
-   Power: Nodes need at minimum a 6V, 3W solar panel plus a battery capable of 3600mAh

Components
----------

All are initial estimations, probably missing a component or two and haven't scoured for bulk prices on everything [Tunabananas](/User:Tunabananas "wikilink"):

-   [ESP8266](https://tinurl.com/y7sytmox) - $2.50
-   LoRa Transceiver - [HackRF RFM95W](https://www.digikey.com/products/en/rf-if-and-rfid/rf-transceiver-modules/872?k=RFM95) - $7 OR \[Dorji DRF1276G\](https://www.tindie.com/products/DORJI_COM/868mhz-915mhz-sx1276-module-drf1276g/) - $6
-   [Custom PCB - ~180x120, 1 layer, 100ct](https://www.seeedstudio.com/fusion_pcb.html) - $6.50
-   [Directional WiFi Antenna 5dBi](https://www.ebay.com/itm/GSM-900MHZ-Omnidirectional-Wireless-Module-Antenna-SMA-Head-5DBI-19cm/281782888586900MHz) - [another option](https://www.tvc-mall.com/details/3w-6v-diy-monocrystalline-silicon-solar-panel-145mm-x-145mm-sku85020025a.html) - $3
-   [Solar Panel - 6V, 3W, 120mAH](https://www.ebay.com/i/121104191012?chn=ps&dispItem=1) - [another lead](https://www.tvc-mall.com/details/3w-6v-diy-monocrystalline-silicon-solar-panel-145mm-x-145mm-sku85020025a.html) - $5-6
-   [LiOn Battery](http://www.dx.com/p/ultrafire-18650-3-7v-3600mah-batteries-pair-50486) - 3.7V 3600mAh - $4

OR

-   LTO battery? - NEED TO RESEARCH COSTS
-   [3.3V buck converter](https://www.adafruit.com/product/2745) - $5
-   Enclosure - ~$5

**\* Total: ~$40**

Documentation
=============

-   Code is here: <https://github.com/sudomesh/disaster-radio-nodemcu>
-   Documentation wiki is here: <https://github.com/sudomesh/disaster-radio/wiki>
-   Network visualization simulation: <https://jemucino.github.io/disaster-radio-netsim/>

Presentations
-------------

[juul](/User:juul "wikilink") gave a [talk about this at the 2017 BATTLEMESH in Vienna](https://www.youtube.com/watch?v=tPJj3zCyRpI). [Slides](http://battlemesh.org/BattleMeshV10?action=AttachFile&do=get&target=disasterradio_juul.odp)

User Research
-------------

[Tunabananas](/User:Tunabananas "wikilink") designed [use cases and user stories](http://wiki.tidepools.co/view/Ethnography) for the decentralized mobile mapping application Tidepools in early 2013, based on open-ended interviews with community residents and various organizations engaged in technology equity and access.

Licensing
=========

-   [firmware/](https://github.com/sudomesh/disaster-radio/tree/master/firmware): Dual licensed under both GPLv3 and AGPLv3
-   [web/](https://github.com/sudomesh/disaster-radio/tree/master/web): AGPLv3

[Category:DisasterRadio](/Category:DisasterRadio "wikilink")