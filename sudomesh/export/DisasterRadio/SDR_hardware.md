---
title: DisasterRadio SDR hardware
permalink: /DisasterRadio/SDR_hardware/
---

Prototypes
==========

Transmitter
-----------

The first transmitter prototype is using the USRP1 with the WBX daughterboard. We've been testing on 500 mhz.

### Antenna

We're using a “christmas tree”-type pcb antenna from Ettus Research.

Receiver
--------

The receiver prototype is the Elonics E4000 which is a $12 (from china) RTL-SDR device.

### Receiver antenna

We're using the antenna that came with the Elonics E4000 which is fine for short distances.

Final radio hardware
====================

Transmitter
-----------

Work is currently in progress to design a cheap radio transmitter that plugs into USB. We're trying to keep the price under $150. We have a few design ideas that need to be added to this wiki. A quick overview of current proposed designs:

Something that takes USB input and spits it out through a 200-500 MSPS DAC. This would limit us to 100-250 mhz (probably realistically more like 50-125 mhz, as you don't want to cut it too the Nyquist limit), but would probably be pretty cheap. This could probably be implemented with a cheap FPGA as the only IC and would be really cheap.

We could also do something that isn't a fully general purpose SDR, using e.g. the [ADL5385](http://www.analog.com/en/rfif-components/modulatorsdemodulators/adl5385/products/product.html) (30 mhz to 2.2 ghz QAM modulator that takes an I/Q input signal) and the [ADF4351](http://www.analog.com/en/rfif-components/pll-synthesizersvcos/adf4351/products/product.html) (35 mhz to 4.4ghz voltage controlled oscillitor). Analog Devices already has a free reference design using these devices. This would mean that the modulation scheme is limited to QAM, but the signal would likely be of high quality and the transmission frequency and power could be varied to a high degree.

### Amplifier

A transmission amplifier will be needed to make a mesh work with only a few of the nodes capable of transmission. We haven't done any work on this yet.

### Antenna

No work on this yet.

Receiver
--------

We will almost certainly use the Elonics E4000 as the final receiver as well.

### Antenna

The antenna will depend on the frequency range we choose for the transmitter. No work has been done on this yet, but the cost should be kept as low as possible.

[Category:DisasterRadio](/Category:DisasterRadio "wikilink")