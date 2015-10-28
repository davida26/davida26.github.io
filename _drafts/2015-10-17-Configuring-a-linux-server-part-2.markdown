---
layout: post
title: Configuring a Linux Server - Part 2
---

https://www.digitalocean.com/community/tutorials/how-to-install-webmin-with-ssl-on-ubuntu-14-04

###Installing SSH

sudo apt-get update
sudo apt-get install openssh-server

Check ssh is working
grep Forwarding /etc/ssh/sshd_conf

###Dynamic DNS (if needed - to access server remotely)

ddclient install

Check ddclient is running
sudo /etc/init.d/ddclient status

Check ip address
ifconfig


###Port Forwarding

This is done at the router level - you will need to port forward port 22, 80, 443, 10000(although this is not recommended - why would you allow webmin access remotely? - ssh and do it yourself)

[Port Forwarding on a Verizon Router](/2015-10-29-Port-Forwarding)



###Webmin
Server management (recommended only for local network)
GUI for server from web


###Server Plan

Virtual Machines
		- Windows 10, Ubuntu, Windows Server (for testing)
	- Media Server
		- Plex + Apps
	- File Server
		- FREENAS (better than adding )


###Creating Partitions

General process: First create partitions, save partition table, create filesystem, mount partition

Using webmin - might give you an error if the label has not been set.
https://techjourney.net/unrecognised-disk-label-when-creating-partition/

Now run webmin
add drives to partitions

If you see an error with the partitions using fdisk -l - it is ok (as long as its working)

{% highlight bash %}

sudo fdisk -l
// Get output from fdisk partition error

sudo parted
//get loop output

{% highlightend %}



