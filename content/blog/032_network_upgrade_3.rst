:title: Upgrading my Home Network Part 3
:summary: In the final part of my network upgrade, I write about choosing an audio player and media centre.
:tags: Networking, Linux
:date: 20150919
:status: published

.. include:: <isonum.txt>

Back in May I `wrote about <{filename}029_network_upgrade_2.rst>`_ choosing a new router and building a network-attached storage (NAS) server. With the network upgraded, I looked at the clients for media playback.

Radio and music
===============

Before upgrading, I used an O2 Joggler to listen to radio in the living room. With the new network in place and a NAS to hold all my music, however, I looked at different options.

Having previously used the Raspberry Pi to run XBMC, I looked around and discovered that there was a project to run a Pi as a dedicated audio player. `Volumio <https://volumio.org>`_ provides a graphical interface to the `Music Player Daemon (MPD) <http://www.musicpd.org>`_. Not only could it connect to my NAS, but it also streamed internet radio.

To go with Volumio, I bought a digital-to-analogue converter (DAC) for the Raspberry Pi, called the `HiFiBerry DAC+ <https://www.hifiberry.com>`_. It simply plugs into the top of the Raspberry Pi and provides either a 3.5 mm phone jack output or two RCA jacks to connect to my amplifier. It takes digital audio from the Raspberry Pi and converts it, producing high-quality audio.

To run Volumio and the HiFiBerry DAC, I bought the small Raspberry Pi Model A+. It has no ethernet connection and only one USB port. This can make set up of software difficult, but once working I simply plug a WiFi dongle into the USB port and leave it alone.

I ran Volumio for about six months. It had some quirks but nothing too frustrating. In particular, it was quite temperamental when it came to connecting to the NAS. It would often need a reboot if there was a problem connecting. It was also quite slow when accessing the GUI, but I put this down to the limited power of the Raspberry Pi.

Recently, I found out about a similar project to Volumio, called `RuneAudio <http://www.runeaudio.com/>`_. I was curious about it and installed it one evening last week. After taking some time to set up, I was very impressed. The look and feel of the GUI is very similar to Volumio but access is much faster. The connection issues are still there but rather than a reboot, I can just connect to the NAS again and all is well.

Volumio is undergoing a `major rewrite <https://volumio.org/introducing-volumio-2/>`_ and I'm looking forward to trying it when it's ready. Until then, however, I think I'll stick with RuneAudio.

TV and films
============

I've not changed much with the playback of films and TV. I upgraded my original Raspberry Pi Model A to a Model B+. This helped run XBMC/Kodi more smoothly, but I now run the `OSMC <http://osmc.tv/>`_ distribution. I love its minimalistic interface and it runs very smoothly indeed.
