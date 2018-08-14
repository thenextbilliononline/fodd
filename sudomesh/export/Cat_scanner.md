---
title: Cat scanner
permalink: /Cat_scanner/
---

Reading all the tags
====================

Someone already wrote a program and made a simple instruction for building the hardware that lets you read every type except for the “Avid Encrypted” tags, which can be read but not decrypted. They also put a web API online for decrypting the Avid Encrypted tags and they have instructions for how to build your own decryptor (they call it a “translator”), however building the decryptor requires a [~$300 piece of hardware](http://www.allvetsupply.com/miun.html). Everything is [here](http://max-gpl.sourceforge.net/).

Standards and “Standards”
=========================

All chips operate at either 125 kHz (ISO) or 134.2 kHz (proprietary) but a scanner using either frequency can read both types:

> Although ISO chips are optimized for 134.2 kHz, in practice they are readable at 125 kHz and the “125 kHz” chips are readable at 134.2 kHz.

-- from [this section on wikipedia](https://en.wikipedia.org/wiki/Microchip_implant_(animal)#Cross-compatibility_and_standards_issues)

ISO 11784 & 11785
-----------------

Includes half-duplex (HDX) and full-duplex (FDX) types. I've seen references to FDX-A and FDX-B but unsure of the difference.

-   juul ordered a bunch of FDX-B chips
-   HDX are available on aliexpress for ~$20 for 10x but haven't been ordered since they are generally not used in pets

Readers retail for ~$150 on ebay.

-   [wikipedia article](https://en.wikipedia.org/wiki/ISO_11784_%26_11785)

Sourcing:

-   juul ordered and received a Hitag S256 chips.
-   juul ordered 10x [FDX-B chips from ebay](http://www.ebay.com/itm/10pcs-EM4305-ISO11784-85-FDX-B-2-12-12mm-RFID-microchip-Animal-glass-tags/302319562649?ssPageName=STRK%3AMEBIDX%3AIT&_trksid=p2060353.m2749.l2649)
-   juul ordered 10x FDX-A aliexpress... maybe. They are listed as both ISO FDX-A and Fecava at the same time. According to [Max](http://maxmicrochip.com/ISO_types.htm) these types are actually using the ISO FDX-A standard but with every bit in the protocol inverted. The ones ordered are more likely ISO FDX-A than true Fecava.

Trovan
------

Also known as Trovan Unique. Also used by some HomeAgain chips and Bayer chips.

We have not been able to source these.

FECAVA / Destron
----------------

Used by:

-   Avid EuroChip
-   24PetWatch
-   Original HomeAgain chip

Sourcing:

-   juul ordered 10x of these from aliexpress... maybe. They are listed as both ISO FDX-A and Fecava at the same time. According to [Max](http://maxmicrochip.com/ISO_types.htm) these types are actually using the ISO FDX-A standard but with every bit in the protocol inverted. The ones ordered are more likely ISO FDX-A than true Fecava.

AVID Friendchip
---------------

Also known as Avid Encrypted.

-   juul ordered a single on of these from ebay. It cost $33 which is why he only ordered one.


juul received it!

Resources
=========

Wikipedia:

-   [Animal microchip implant](https://en.wikipedia.org/wiki/Microchip_implant_(animal))
