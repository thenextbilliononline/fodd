---
title: File server
permalink: /File_server/
---

There is a file server on [space.local](/Space_Server "wikilink").

It is 650 GB on an external USB harddrive and completely read/writable to anyone in the space.

Access using SFTP
=================

Ubuntu
------

Open the [file manager](https://en.wikipedia.org/wiki/Nautilus_%28file_manager%29) and in the top menu (all the way at the top of the screen) choose “File -&gt; Connect to Server”. Fill out the dialogue box like so:

-   Service type: SSH
-   Server: space.local
-   Folder: data
-   User Name: sudoer

You can choose to add a bookmark so you don't have to fill out the dialogue every time.

The password is: sudoer

Mac OS X
--------

You don't need to download any programs. Just go to your finder, scroll down to the shared area and you'll see space. Login as a guest, no password needed.

[On a mactinosh just click on finder and then you have access to space.local](/File:Space.local_on_a_Mac.png "wikilink")

### FTP from a Mac

You can use the free [Cyberduck](http://cyberduck.ch/) program.

-   Server: space.local
-   Username: sudoer
-   Password: sudoer

Windows
-------

On Windows, it's probably easier to use Windows filesharing (see below). If you for some reason prefer SFTP, you can use the free/open [WinSCP](http://winscp.net/) software.

-   Server: space.local
-   Username: sudoer
-   Password: sudoer

Access using SMB/CIFS (Windows filesharing)
===========================================

WE SWITCHED SERVERS! Some of this information maybe inaccurate, but the information for Lubuntu has been verified.

Ubuntu (Nautilus file manager)
------------------------------

In the [file manager](https://en.wikipedia.org/wiki/Nautilus_%28file_manager%29), make sure the side pane is open (if not, hit F9 to toggle the side pane). Click “Network” in the side pane, then “Windows Network”, then “Workgroup”, then “SPACE” and finally “sudoshare on 192.168.42.1”. You can now browse the available data and upload new data by dragging the files to the window.

Lubuntu (PCMan file manager)
----------------------------

In the file manager address field, enter:

` `[`smb://192.168.42.1/`](smb://192.168.42.1/)

Wait. It might take a while and it will seem like nothing is happening. Once the icons show up, double-click the sudoshare folder.

Windows General
---------------

[thumb|300px](/File:Files_server_screeenshot.PNG "wikilink") Go to start -&gt; run. In that box write “\\\\SPACE”. You should see a folder. The default username/password *guest/guest* give you read and write access.

Windows XP
----------

Just go to “My Network Places” and “sudoroom public data on space server”. You can now browse the available data and upload new data by dragging the files to the window.

If it asks for a username and password, they're both “guest” (without the quotes).