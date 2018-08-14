---
title: Brother HL-2270DW
permalink: /Brother_HL-2270DW/
---

It's a networked printer. Most operating systems will find it automatically if you're connected to Omni wifi (sudomesh, Omni Ballroom, etc). If you have trouble over the network, you can also connect by USB.

Details
-------

Model: Brother HL-2270DW
Model website: <http://www.brother-usa.com/Printer/ModelDetail/1/HL2270DW/>
[user guide](http://www.brother-usa.com/VirData/Content/en-US/Printers/Consumer/UsersManual/UM_HL_2220_2230_2240_2240D_2270DW_EN_2640.PDF)
[network user's guide](http://www.brother-usa.com/VirData/Content/en-US/Printers/Consumer/NetworkUsersManual/NUM_HL_2270DW_EN_2639.PDF)
Features: B&W laser duplex wifi
wifi mac address: 00:22:58:18:DD:FD
ethernet mac address: 00:1B:A9:56:22:ED

Configured to connect to the SSID “sudomesh” with static IP 192.168.42.12

You can access its web interface from the sudo network: <http://192.168.42.12/printer/main.html>

The default user is “admin” and its password is “access”.
Original listserv announcement: <http://lists.sudoroom.org/pipermail/sudo-sys/2013-December/000144.html>

**HELP! how do i stop it printing stuff nobody wants?**
-------------------------------------------------------

if you're printing from linux, try emptying your local print spool by typing `lprm`

also try the printer's web interface maybe

bare-metal linux instructions
-----------------------------

1.  Install & run [CUPS](https://www.cups.org/)
    -   On Ubuntu/Mint:
        -   `apt-get install cups`
        -   `service start cups`
    -   On Debian:
        -   `apt-get install cups`
        -   `/etc/init.d/cups start`
    -   On Arch Linux:
        -   `pacman -Syu cups`
        -   `systemctl start cups`
2.  You configure CUPS through the browser at: <http://localhost:631/admin>
3.  Click on `Add Printer`. It will ask you for your root password. This is very insecure but it's how some stupid Linux things work!
    -   User Name: root
    -   Password: your root password
4.  Under **Other Network Printers**, select: `LPD/LPR Host or Printer` and press `continue`
5.  Under **Connection**, enter this string: `lpd://192.168.42.12/queue`
6.  Choose a name, description & location you will remember, then press `continue`
7.  Under **Make**, select Brother. Press `continue`.
8.  Under **Model**, select: `Brother HL-1250 Foomatic/hl1250 (recommended)`.
9.  Press `Add Printer`.
10. Try printing a test page!

Getting More Toner
------------------

Bring the empty toner cartridge to [Cartridge World](http://www.yelp.com/biz/cartridge-world-oakland) and they will give you a full one for $50ish. They reuse the cartridges. They've always had plenty of this model in stock. If you know of a cheaper alternative please edit this wiki.

It's just down the road, 1.5 miles away. [Directions](https://www.google.com/maps/dir/Sudo+Room/Cartridge+World+Rockridge)

Make sure you bring just the cartridge and not the entire drum thing. Those are more expensive and breakable.

Duplex Mode
-----------

Duplex mode is when it prints on both sides of the page. You can turn this on/off at the web interface: <http://192.168.42.12/user/prnset.html>

In duplex mode, I advise printing just one copy at a time. If you try to print multiple copies in one job, it might collate them wrong. This just happened to me. I tried to print two copies, but each sheet had the same exact thing front & back. Very weird.

Network Fail
------------

Sometimes the network settings get fucked up because someone factory reset it or something. You can print the current settings by pressing **Go** 3 times within 2 seconds. If it got factory reset, the IP address will probably be `169.254.32.12` so you can fix it by connecting your linux laptop directly by ethernet and then something like:

`sudo ip link set eth0 up`
`sudo ip addr add 169.254.32.11/16 broadcast 169.254.32.255 dev eth0`

Then visit the [settings page](http://169.254.32.12/printer/main.html) in your browser. The default auth is:

`Username: admin`
`Password: access`

### Fixing the settings

Tell wifi to use sudomesh:

-   <http://169.254.32.12/bio/wlan.html>
    -   Wireless Network Name (SSID): sudomesh

Then change the wifi TCP/IP settings:

-   <http://169.254.32.12/bio/tcpip2002.html?interface=2>
    -   IP Address: 192.168.42.12
    -   Gateway: 192.168.42.1

Then make it use the wifi instead of ethernet:

-   <http://169.254.32.12/bio/multiif.html>
    -   Auto Switching ( Enable Both Interfaces )

The printer will restart and the page won't reload. But now wifi should work. For some reason you can't have wifi + ethernet at the same time.