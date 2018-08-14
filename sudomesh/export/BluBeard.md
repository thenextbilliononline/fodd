---
title: BluBeard
permalink: /BluBeard/
---

    .______    __       __    __  .______    _______     ___      .______       _______
    |   _  \  |  |     |  |  |  | |   _  \  |   ____|   /   \     |   _  \     |       \
    |  |_)  | |  |     |  |  |  | |  |_)  | |  |__     /  ^  \    |  |_)  |    |  .--.  |
    |   _  <  |  |     |  |  |  | |   _  <  |   __|   /  /_\  \   |      /     |  |  |  |
    |  |_)  | |  `----.|  `--'  | |  |_)  | |  |____ /  _____  \  |  |\  \----.|  '--'  |
    |______/  |_______| ______/  |______/  |_______/__/     __\ | _| `._____||_______/

<big>2U Dual AMD Processor Rack Server</big> aka: Mark IIIR Net Integrator

[<File:BluBeardHello.jpg>](/File:BluBeardHello.jpg "wikilink")

[thumb|right|Initial boot BIOS screen.](/File:BluBeardBIOS.jpg "wikilink")

[thumb|right|RAM module.](/File:BluBeardRAM.jpg "wikilink")

[thumb|right|SCSI Hard Drive label.](/File:BluBeardSCSI.jpg "wikilink")

Blah blah blah...

Motherboard: TYAN Thunder K7X (S2468) <http://www.tyan.com/archive/products/html/thunderk7x.html>

Brochure: <http://www.jadecomputers.us/Files/markiiir.pdf>

Maintenance
-----------

### Setup

-   Burn current ISO of Arch Linux to CD <https://www.archlinux.org/download/>
-   Boot off CD using external USB CD-ROM drive (may require boot order mod in BIOS)
-   Connect ethernet cable to Ethernet Port 1 (enp2s8)
    -   run `# dhcpcd` to start DHCP assignment
    -   test connection with a ping `# ping -c 3 www.noisebridge.net`
    -   Now we know the puter fires up and connects to the internets
-   Power off and run GParted to setup partitions `systemctl poweroff`
    -   From GParted configure `/dev/sdg` as gpt partition with fat32 and boot flag
        -   This is a 256MB Flash Drive
    -   Create and configure SCSI Hard Drives (/dev/sda thru /dev/sdf)
        -   Configured /dev/sda & /dev/sdb with gpt table, 10GB fat32 boot and 130GB ext4
-   Reboot with Arch Linux
    -   Mount root
        -   `# mount /dev/sda1 /mnt`
    -   Mount home
        -   `# mkdir /mnt/home`
        -   `# mount /dev/sda2 /mnt/home`
    -   Mount UEFI
        -   `# mkdir -p /mnt/boot`
        -   `# mount /dev/sdg1 /mnt/boot`
-   Install linux base
    -   `# pacstrap -i /mnt base`
        -   Select default (all), about 160MB download, 450MB install
-   Generate fstab
    -   `# genfstab -U -p /mnt >> /mnt/etc/fstab`
    -   `# nano /mnt/etc/fstab`
-   Chroot
    -   `# arch-chroot /mnt`
-   FAIL
-   FAIL!
-   FAIL!!!!!!!!!!!

### Log

Installed Arch Linux July 1, 2013 build [Thex](/User:Thex "wikilink") ([talk](/User_talk:Thex "wikilink")) 16:21, 18 July 2013 (PDT)

[<File:BluBeard2U.jpg>](/File:BluBeard2U.jpg "wikilink") [Category:Hardware](/Category:Hardware "wikilink")