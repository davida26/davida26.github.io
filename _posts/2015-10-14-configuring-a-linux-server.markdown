---
layout: post
title: Configuring a Linux Server - Part 1
description: Simple walkthrough of setting up a linux server. Basic introduction to Ubuntu LTS 14.04 installation options.
---

<strong>Part 1 - Basic Linux Server Install</strong>

We will go through the entire installation process from creating a bootable USB drive to setting up a basic Linux Server. Part 2 will cover partitioning our drives (more advanced) and installing packages. 


### 1. Create a bootable USB Drive

Download the distro of Linux that you are looking for. Use [Unetbootin](https://launchpad.net/unetbootin) to create a bootable USB drive. In my case I am looking for Ubuntu Server Latest Version - 14.04 at the time of writing.

When you are downloading Ubuntu Server, make sure you support the guys at [Ubuntu](http://www.ubuntu.com/server) with a small donation. Whether its for home or work, remember that it took a team of people time to build what you are using. 

Anyway, setting up the bootable USB drive is easy. The Unetbootin UI gives you the options to use an exisiting one or select yours. Do as needed here. I am using the Ubuntu Server file I downloaded right from Ubuntu.

### 2. Boot Your PC with USB

Plug your bootable USB drive and turn on your computer.  If it does not boot through the USB, you need to change the BIOS so that USB is the first boot device. You can access the BIOS hitting F2 (may be different on some PCs).

### 3. Unetbootin Linux Setup

Once your PC can boot from the USB. Start by selecting the *Install* option. You may see install Ubuntu Server below that but that sometimes causes the bootloader to fail - so don't use it if you are following my process. Current process: you loaded your own copy of Ubuntu Server to Unetbootin, so the install option will work and install Ubuntu Server as it is the only copy it has.

Run through the steps, that apply to you:

- Language: English
- Country: US
- Keyboard: here you have the option to let the installer detect your keyboard by prompting you with a few questions or to manually select it. Select NO and select your language for the keyboard, location and configuration. It is faster.

### 4. Installation Process & Configuration

This takes a few minutes depending on your machine so grab yourself a cup of coffee or in my case hot chocolate to begin. 

Linux will start by identifying your Network. 

*Note - you should have your pc connected to a network so you can access the Internet to install necessary packages.*


<strong>Hostname</strong>
It will prompt you for a hostname - name this anything you want. In my case I will call this server *office.* Now if you are planning on adding more servers down the road. Name it something you can recognize and will help you differentiate it from the others.

<strong>Ubuntu Archive</strong>
Once you are done with that it will prompt you for a country for an Ubuntu Archive Mirror and then give you the option to select a mirror.

<strong>Proxy</strong>
Prompts you for a proxy if you are using one to connect to the internet. I am not using one so I left that blank. 

<strong>Admin Account</strong>
It will run through a few installs and then ask you to setup an admin account. You can name it anything you like. Then create a user for that account and finally set a password. By default Linux will secure the "root" account by forcing you to create your own from which you can perform administrative tasks. So intead of loggin in as root, you login with your username.

<strong>Home Directory Encryption</strong>
Basically adds a layer of security if your computer is stolen. In most cases, you will not need this and configuration down the road is more difficult if you select yes. For my purpose, I am selecting no.

<strong>Configure the Clock</strong>
Linux will attempt to identify the present location of your server. Adjust for correct time zone as needed here.

<strong>Partition Disks - Remove USB</strong>
If you are using the USB boot, it will detect is as:

``` shell

/dev/sda

```

Select the option to unmount it since it will no longer be needed.

<strong>Partition Disks -  Set up your drives</strong>
Now you will be prompted to select the type of partition needed. You have a few options here including:

- Guided: resize X (0,0,0), partition #1 (sda) and use free space (X is a drive)
- Guided: use entire disk
- Guided: use entire disk and set up LVM
- Guided: use entire disk and set up encrypted LVM
- Manual

I usually select Guided: use entire disk and set up LVM. Why? Because with LVM (Dynamic Partition) you can expand or shrink the partitions as needed. More information can be found [here](http://askubuntu.com/questions/3596/what-is-lvm-and-what-is-it-used-for)

If you selected Guided LVM, enter how much of the Volume you want to use. LVM is dynamic so dont worry about partitioning too much or too little.  You can always modify this down the road and best practice is: less is more. Easier to expand than shrink.

Now let it create the partition tables and installation of the base system will begin.

<strong>Configuring Discover</strong>
Aka configuring updates. You have a few options here:

- No automatic updates
- Install security updates automatically
- Manage system with Landscape

Recommended: Install updates automatically unless you have a system where the updates can break your setup or have experience with Landscape. 

<strong>Software Selection</strong>
Now you have the "core" system installed. Ubuntu will now give you options to choose software to install. You can install anything you like for your needs but the recommended step here is:

Install OpenSSH Server - this will give you the ability to ssh into your server and since most people configure their servers to be headless (no monitor), this will come in handy.

<strong>GRUB Boot Loader</strong>
The Ubuntu instructions are self-explanatory. The installer detected no other systems so install GRUB. 

WARNING: MAKE SURE YOU UNPLUG THE USB YOU ARE BOOTING FROM. Keep that for you, for another project or when you blow up your current install. The installer will override everything on the USB if you don't remove it.

### Installation Complete

Now you can enter the username you created and the respective password. Say hello to your new Ubuntu Server. #win







