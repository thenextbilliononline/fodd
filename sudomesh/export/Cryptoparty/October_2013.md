---
title: Cryptoparty October 2013
permalink: /Cryptoparty/October_2013/
---

Intros
======

What are you interested in talking about?

-   Email encryption
-   Bitcoin
-   Alternatives to OTR using GPG
-   Open Wireless and encrypted wifi networks
-   Local encrypted storage with git
-   Browser security
-   Simplify security process for activists \[eg; 'digital security hygiene toolkit'\]
-   Security in general - how to talk to people who don't think security is important
-   Homomorphic Encryption project, talk to Ryan Jarvinen @ryanj
-   BREACH and dealing iwth HTTP compression working arounds including sanitizing the response body.
-   Does Firefox trust the Chinese government to not forge a fake Certificate through the CNNIC certificate authority
-   Convergence.io discussion / review / vulnerabilities
-   Hashed.im hackathon

First Chat
==========

-   How to talk to people about why security is important
-   Why, as a general concept, is security important? For instance, assumption is that Google is secure, etc.
-   Why should this matter for me, even if I agree it's important in general? For instance, you're not going in to a field where security matters (e.g. physics). But imagine a scenario where you simply meet someone who at some point becomes a target by authorities, including the US government, etc. In this situation, it becomes very difficult and unsafe to communicate, need to invest in security for your protection, and the protection of your community. It belongs to the community, not necessarily individuals, even if you're not personally going to do anything wrong. You may become a victim of surveillance, a target by proxy or by association.
-   Further, you don't even need to break the law to become a victim of surveillance. For instance, in Sweden, a complete list of Roma was created (discrimination).
-   Legislative change could occur, in which your legal activities today could become illegal tomorrow, especially in the context of a dragnet where your history may come back to haunt you.

Solutions:
----------

-   Look to maintaining institutions that do not make it easy for corruption to take hold.
-   So what do you say to someone who doesn't take security seriously?
-   E.g. the “The NSA probably has good reasons” - examples like activist Jacob Applebaum can help. On the other hand, a metaphor of “safe sex” using condoms is straight to the point.
-   E.g. Another tactic is hygiene, protection against infection.
-   E.g. Also, the community argument holds to remind that you may be putting others at risk.
-   E.g. Martin Luther King Jr.'s historical record of surveillance from the US government is a retrospective example of the affects.
-   Does secure communication highlight you as a target?
-   Interestingly, by using secure and encrypted communication, perhaps you can contribute to obfuscating very sensitive secure and encrypted communications, even if yours is not.
-   Also, tacitly, you use encryption all the time. There are lots of implemented security systems in place. Often this indicates that you in fact will not appear as a needle in a haystack.
-   Further, you can use strong encryption inside of other encrypted methods (like TLS), which obfuscates the level of security in use.
-   Ultimately, it depends on how you use it, and it's possible to flag you. On the other hand, this does bring up the fundamental concern about privacy and secure communication: is it necessary and valuable?
-   Encrypting everything can help obscure
-   The more people who use encryption, the lower the cost becomes for using it ;)
-   ON THAT NOTE, WELCOME TO CRYPTOPARTY!

Rhodey on SSL / Certificate Authorities
=======================================

-   SSL / TLS handshake
-   Certificates are public keys used to authenticate
-   At this step, the session can be man-in-the-middle'd
-   The site decrypts the pre-master secret using its private key, then both the user and the site calculate the master secret and generate two session keys, one for encyrption, the other for decryption
-   Security Vulnerabilities: SSL 2.0 \[DO NOT WANT\], TLS 1.1 & 1.2 not widely supported
-   Security patches: Disable renegotation; BEAST \[disable or sandbox Java in the browser\]; CRIME \[disable TLS Compression\]

Jae Kwon on Scramble.io, Certificate Authorities, and Perfect Forward Secrecy (TLS v1.2)
========================================================================================

-   There are 458 certificate authorities trusted by Ubuntu Linux (operating system) by default. Any one could be compromised to generate fake certificates and access all seemingly secure communication.
-   <http://convergence.io> uses a Notary Model instead of the Certificate Authorities model. Somewhat unmaintained project.
-   What convergence.io misses is what is provided by “Perfect Forward Secrecy”
-   Without Perfect Forward Secrecy, if you store communication now and are able to get ahold of the private key later, you could decrypt it then. This is called “retroactive decryption”
-   Services that previously offered secure email services that have since shut down, notably surrounding NSA surveillance programs, i.e. PRISM.
    -   Lavabit
    -   Silent Circle
    -   TorMail
    -   HushMail
-   One way to deal with this circumstance is to create a service that is not dependent on the server, that is open source, decentralized, and using good crypto.
-   Good crypto?
    -   RSA2048
    -   RSA2048 + AES128
        -   Rob Schneir says this is okay.
            -   just a thought but:

(isn't this a typo for Bruce ? er Bruce Schneier of <https://www.schneier.com/crypto-gram.html> crypto-gram newsletter?) correct me if i'm wrong =)\]\]

-   -   OpenPGP

How it works:
-------------

-   Create a message.
-   Generate an encrypted session key (AES)
-   A session key is used as a matter of performance
-   Encrypt the message using that session key
-   Use the recipient's public key to encrypt the session key itself!
-   Then you can send your encrypted message which can be decrypted in the reverse process with the recipients private key once they get the message

Bill on OTR
===========

-   Real-time encryption system widely implemented in instant messaging applications
-   Transport-layer agnostic
-   Enables multi-party communications
-   Attackers can see who the communicating parties are, but not what they've said
-   These advantages mimic spoken conversation among friends (web of trust model)
-   OTRv3 released in 2012
-   Diffie-Hellman to establish shared keys
-   A way to establish a zero-knowledge secure session over a plaintext transport layer.
-   Mathematical principle: it is easy to multiply 2 large primes to arrive at a large prime-product, but difficult -
-   Identity verification is a crucial step! Verify fingerprints (eg; PGP) or Socialist Millionaires Protocol
-   New in v3: Extra derived key for secure file transfer, voice chat (!!) \[not yet implemented\]
-   Spec Implementations:
    -   C: libotr
    -   Java-otr (no longer maintained)
    -   Javascript otr (new!)
    -   Applications w/ native support: Adium, Bitlbee
    -   Plugin support: Pidgin, Kopete, Trillian, irssi, WeeChat, XChat
    -   The future: mpOTR (multi-party OTR)

Lightning Talks
===============

Bill on Verifiable Builds
-------------------------

-   Apt-get install is not the most trusted way of installing software, as it was pre-compiled on another machine
-   Post by Perry from Tor Project: <https://blog.torproject.org/blog/deterministic-builds-part-one-cyberwar-and-global-compromise>
-   Deterministic builds

Yan announces 2nd Aaron Swartz Memorial Hackathon
-------------------------------------------------

-   November 8-10 at Noisebridge
-   AaronSwartzHackathon.Org[1](https://AaronSwartzHackathon.Org) for more details

Cryptoreddit
------------

-   <http://reddit.com/r/cryptoreddit>
-   Apply PGP to Reddit threads
-   WiFi Probe Requests and Responses
    -   Open database linking GPS coordinates to MAC addresses
    -   WiFI Pineapple - <http://hakshop.myshopify.com/products/wifi-pineapple>
-   <http://lockboxx.blogspot.com>

Jake on PGP-authenticated Voting
--------------------------------

-   Public keys for signing should be signed by a trusted registrar
-   These registrars would have to resign keys in person each year; keys expire after one year
-   Yet they would still be anonymous even from the registrar \[signed using gnuk\]
-   Needs a super-simple, easy to use front end - 'as simple as making a facebook profile'

Running Code Securely Using Emulation
-------------------------------------

-   68K emulation
-   very simple

Resources
=========

-   Surveillance Self-Defense (SSD) to be updated in the coming months)
-   Prism-Break: <http://prism-break.org/>
-   StopWatching.Us
-   CryptoStick - <https://www.crypto-stick.com/>
-   KeyDroid - <https://play.google.com/store/apps/details?id=com.ekp.androidsw.keydroidintads&hl=en>
-   AppArmor - <https://wiki.ubuntu.com/AppArmor>
-   strace - <http://en.wikipedia.org/wiki/Strace>
