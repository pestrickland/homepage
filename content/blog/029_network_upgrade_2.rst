:title: Upgrading my Home Network Part 2
:summary: Following the overview of my upgrades, I write about router choice and building a NAS server.
:tags: Networking, Linux
:date: 20150524
:status: published

.. include:: <isonum.txt>

In my `last post <{filename}028_network_upgrade.md>`_ I summarised the changes I made to my network. Two of those changes were buying a new router and building a network-attached storage (NAS) server. This time I'll go into a bit more detail about my current solution and list the resources that helped me.

Router selection
================

My previous router was a cheap generic affair that I'd been using for the past seven years. It worked, but it was not that fast and it was not ideally located either; my flat is long and narrow with the router installed in the front corner surrounded my pipes, and my main use of the internet occurring at the back. Although not a large place, I wanted a reasonably powerful router to overcome the drawbacks of its location. Since I was also planning to have a NAS attached to it to stream all my data, performance was also quite a priority.

A few years ago I was very keen to find a Linksys WRT54G series router in order to run third party firmware such as DD-WRT. And looking through recent router reviews, the Linksys EA6900 was very appealing. I was extremely tempted to buy that one before I saw more favourable reviews for the D-Link DIR-880L. At a competitive price but with a better rounded set of good reviews, I decided to purchase the D-Link router.

Having spent the last few years seeing only small routers, the size of the D-Link was a surprise. It is perhaps 30% larger than a standard home router and comes with three large antennas. Set-up of the router was painless and the administration interface was fairly easy to navigate as well. I had considered looking at third party firmware for it, but so far I have had perfectly acceptable results from the standard firmware.

NAS build
=========

The biggest expense of this project came from building a new computer. I could have simply bought a NAS device, but a fully-fledged server seemed more flexible and also a bit more enjoyable. To aid my selection of components I found the `DIY NAS series of posts <http://blog.brianmoses.net/categories/diy-nas/>`_ by `Brian Moses <http://blog.brianmoses.net>`_ very helpful. My needs were less demanding, and I didn't want to spend more money than I had to. With that in mind I bought the following:

* BIOSTAR NM70I-1037U motherboard (dual core 1.8 GHz Celeron)
* 2 |times| 4 GB DDR3 RAM
* 1 |times| Western Digital Red 1 TB hard disk drive (HDD)
* 1 |times| Toshiba 1 TB HDD
* CFI-A7879 4-bay chassis

In addition I used up two other 500 GB HDDs that were in my desktop, replacing those with a solid state drive.

Clearly, my data storage requirements are not great, but the four-bay case will allow me to upgrade when I need to.

Originally I was tempted to use FreeNAS or NAS4Free to run on a USB flash drive inside the case. One or the other seemed to be a common choice for such applications, and they offered the ZFS filesystem with its reported reliability for a storage set-up. All my data, however, was stored on existing drives using the EXT4 filesystem, and while I probably could have shuffled the data around amongst my available storage, it would have been awkward. Finally, I am familiar and comfortable using Linux, especially Ubuntu, whereas both NAS4Free and FreeNAS run on FreeBSD. I chose the simple option and installed Ubuntu 14.04 Server on the box, installed onto an 8 GB Kingston DataTraveler, my preferred flash drive.

The NAS server sits in a cupboard next to my router, and I access it over SSH. Ubuntu's version of Screen, Byobu, is helpful here as it allows the user to detach from a terminal without logging out. This means I can leave a session and return to it later on.

I chose to use `SnapRAID <http://snapraid.sourceforge.net>`_ and `mhddfs <https://romanrm.net/mhddfs>`_ on my NAS server. SnapRAID provides some protection against HDD failure by taking snapshots of the parity data across multiple drives. mhddfs provides a way of combining multiple areas of storage into a sort of virtual drive.

SnapRAID uses one of my four HDDs to store parity information, leaving three drives to store my data. mhddfs uses the pool of three HDDs to produce one folder that I then share on the network using NFS. So far, it's worked well, although the mhddfs system seems to disconnect at times.

To keep SnapRAID working effectively, I use a script to synchronise my data each night. This came from Zack Reed and can be found `here <http://zackreed.me/articles/83-updated-snapraid-sync-script>`_. He has also written about a number of other utilities such as health monitoring scripts that allow the server to email me if there is a problem.
