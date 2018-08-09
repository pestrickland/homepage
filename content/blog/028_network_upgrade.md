title: Upgrading my Home Network
summary: In a brief overview I write about the changes to my network and the use of Raspberry Pi computers for playing music and video. I built a NAS server to handle all my media and upgraded my router to handle the extra traffic.
tags: Linux, Audio
date: 20150308
status: published

Over the last few weeks I've been upgrading my home network and the means to view and listen to the media I like. What started as a simple loss of internet radio has grown into quite a bit more, but I've ended up with a much improved solution.

##Previous set-up

For the last couple of years I've had more or less the same set-up in my house. Last summer I had my internet connection upgraded from ADSL to a faster fibre-to-the-cabinet connection. I tried to use the router supplied by the ISP but was not impressed by its signal strength and so I went back to my very old (802.11*g*!) router.

The main digital media I consume are digital radio (BBC 6Music) and television downloaded from the BBC iPlayer. I also have a music collection that consists of a mixture of vinyl, CDs and digital downloads.

###Radio and music

The radio was predominantly provided by my old O2 Joggler, a lovely little bit of hardware that was a picture-frame-style device with a touch screen, wireless network adapter and audio out. The audio could be connected to my Hi-Fi speakers in the living room. This worked well until the BBC radio streams changed format. I could still listen to the radio using an Android app on my tablet or phone, but I started to think about a better solution.

My music collection was all available on my desktop PC, and as I spend a lot of time using it, I was able to listen to what I wanted quite easily. Listening to music in the living room, however, limited me to either a CD or a record.

###TV and films

To play TV and films I used a Raspberry Pi with XBMC installed via the Raspbmc distribution. The TV and films were stored on an external USB hard drive and the Raspberry Pi ran get-iplayer overnight to download the programmes I was interested in.

My Raspberry Pi was an original Model B that only had 256 MB RAM. It's a very impressive little computer, but part of me felt that I wasn't using it for what it was intended.

##My new set-up

Here is a summary of my new set-up. If time permits, I'll write more about each item in a later article.

###Networking

Although the idea of running Ethernet throughout my house was appealing, I managed to convince myself otherwise for the time being. I changed two things:

1. Replaced router
2. Built a NAS server

I replaced my ageing no-brand router with a [D-Link DIR-880L](http://www.dlink.com/uk/en/home-solutions/connect/routers/dir-880l-wi-fi-ac1900-router "D-Link DIR-880L Wireless AC1900 router"). It's an impressive device so far, and more than capable to serve my needs.

The NAS server was built after deciding to try consolidating all of my media. Currently it runs Ubuntu 14.04 and primarily acts as an NFS server. It holds my music and video collections.

##Media playback

Wanting an opportunity to use the Raspberry Pi in more of a development and experimental role, I bought another to take over my media centre requirement. In fact, I bought two: one Model B+ and one Model A+.

The Model B+ runs the final release of Raspbmc that runs Kodi, the new name for XBMC. Rather than being connected to a USB drive, I access the NFS server over the network and stream my videos to the Pi. I also moved the get-iplayer task off the Pi and onto the NAS.

I bought the Model A+ after finding out about two things. Firstly, a DAC built for the Raspberry Pi called [HiFiBerry](http://www.hifiberry.com/dacplus "HiFiBerry DAC+") that acts as a sound card to produce high-quality audio. Secondly, a dedicated audio player distribution called [Volumio](https://volumio.org/ "Volumio Audiophile Music Player"). Essentially this allows me to stream my music over the network and into my Hi-Fi.

##Summary

This post is just intended to provide an overview of the changes I made to my home network, and in the future I'll try to provide some more detail about my experience and what I'd recommend to others.

In the space of a fortnight I've changed my disparate and incomplete media providers into something more logical. With an improved network I can now stream all my media to dedicated devices. The biggest change for me has been the use of Volumio and being able to play all of my music on my Hi-Fi speakers is fantastic.

It hasn't been a painless change, but I'm reasonably pleased with how it went. Once the remaining creases have been ironed out I'll be very satisfied.
