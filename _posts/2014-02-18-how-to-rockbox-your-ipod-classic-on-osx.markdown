---
layout: post
title: "How to Rockbox your Ipod Classic on OSX"
date: 2014-02-18 10:51
comments: true
categories: audiophile 
keywords: rockbox,ipod,classic,osx,mac,audiophile
descripton: How to install rockbox on your iPod classic using OSX.
---
Last year I finally bought a decent pair of headphones. I bought the [Koss Porta Pro headphones](http://www.head-fi.org/products/koss-portapro-headphones-semi-open). I chose these because of the huge backing the [Head-fi](http://head-fi.org) community has behind these inexpensive and great sounding headphones.

Due to my budget, I could not afford a nice high quality portable music player to play my flac files. So I thought I would be resourceful. I researched online and found a ridiculously awesome project called [Rockbox](http://www.rockbox.org). They've been around for quite a while and the software completely opens up what is otherwise a closed device - the iPod. 

So here is how I did it on my MacbookPro. This is more easily done on a Windows/Linux machine (especially for managing your music).

*Disclaimer: I am not responsible if you brick your device. This is mearly a guide to how I did it on my iPod classic.*

**Note:** Much of this guide was taken from this [thread on head-fi](http://www.head-fi.org/t/532426/ipod-classic-rockbox-its-happening). Give those guys credit over there.


**Step 1:** 

Get access to a Windows/Linux machine. (If you absolutely do not have access to these, you can do these steps through a vm with [virtualbox](http://www.virtualbox.org). Virtualbox is free, and you can install windows or [ubuntu](http://www.ubuntu.com) *ubuntu also being free*.)

**Step 2:** 

Follow this guide to [install EmCORE](http://freemyipod.org/wiki/EmCORE_Installation/iPodClassic).

1.This is a step by step guide that will guide you through the entire process of installing EmCORE. Just follow the instructions and it is pretty painless.

2.At the second step, be sure to select the most recent emCORE version **(r859)** from the Releases page. *This is extremely important to get it working on your iPod*


**Step 3:** 

When you get to the bullet point saying Download the **"rockbox-ipodclassic.zip"** file, download this file. [Rockbox-ipod6g.zip](http://build.rockbox.org/data/rockbox-ipod6g.zip)

**Step 4:** 

Once you have finished downloading rockbox and unpacked it, you should have a <code>.rockbox</code> folder. Plug in your iPod to your computer and drag the <code>.rockbox</code> to the root of your iPod.

**Step 5:** 

Reboot your iPod. Voila, you have Rockbox.

##Managing your iPod with OSX
Installing Rockbox isn't that difficult. The trickier part is managing your new ipod with the rockbox firmware on top of it. 

**Note: To get OSX to detect your iPod at all please do the following.**

1. Boot up your Rockboxed iPod
2. Scroll right until you get to **Tools**
3. Select **EmCORE Backup Image**
4. Plug your iPod in.

This is currently the only way to get OSX to recognize your iPod as a USB device. You will need to do this each time you sync your ipod with your computer.


There are a couple ways to setup sync so that you can plug your iPod into your mac without having to go to a windows/linux computer or booting up virtualbox. These are the ways that I have found are the most effective.

**Free Options:**

**Nightingale Music Player**

iTunes is really the go-to music player on OSX. It is hard to find quality music players that integrate so well within its operating system. However, since I am using my Rockboxed iPod mainly to play my high quality .FLAC files, I will need something that manages my .mp3 library along with my .FLAC seamlessly.

This is where [Nightingale](http://getnightingale.com) comes into play. 
>**Nightingale chirps your favorite tunes! **

>A beautiful interface with a wide range of supported audio formats, all with multi-platform support! 

Nightingale is a beautiful open source music player that is cross platform. It is a fork of the original **Songbird music player** that shut down early 2013. Nightingale is continuing its legacy and doing an excellent job at it. It manages my 4000+ songs quickly and effeciently. This is the first option I'd reccomend to not only managing your audiophile library, but also syncing it to any device that uses rockbox.

**Instructions to setup Sync:**

1. Open Nightingale
2. On the left hand side, click the button that says **Synchronization**
3. Make sure your iPod is plugged in and detected by OSX.
4. Select a new profile for your iPod and choose what you want to sync.
5. Click **Start Sync**

**Manual Drag-n-Drop**

Of course, you can always revert to the old school drag-n-drop method. You pick what you want and transfer it over. This method is the worst if you have a large library and wish to keep it synced all the time. I would only reccomend this if you need to throw music on quickly.

**Paid Options:**

**Hazel File Management**

[Hazel](www.noodlesoft.com/hazel) is one of my must have applications for OSX.
Put simply, its:
> Automated Organization
for your Mac

Hazel is an automation machine. You can setup specific rules for different events that will trigger responses set to your liking. I could write a whole different post just on the power of Hazel, but I won't get into that now.

Why would you use Hazel? Well quite frankly, some people have an attachment to different audio players that won't necessarily sync with portable drives. Maybe you use the highly popular [Vox](http://coppertino.com/vox/) or a more expensive option [Amarra](http://www.sonicstudio.com/amarra/). With Hazel, you don't have to be tied to any music player. You can simply set where your music is stored and it will sync.

 Here is a profile of how to setup Hazel to sync your ipod every time it is connected automatically.

**Hazel Profile:**

1. Create a new Profile for the <code>folder</code> where your <code>music</code> is stored.
2. If <code>all</code> of the following conditions are met.
3. <code>Kind is Folder</code>
4. Do the following to the matched file or folder
5. <code>Sync</code> into folder <code>(location of your rockbox ipod drive)</code>

It is as easy as that. Everytime your iPod gets plugged in, it will automatically sync any new tracks added. This is really a set it and forget it option. The reason I have it set to "Kind is a Folder" is because I have all of my music organized like so:
Music > ArtistName > AlbumName > Song.mp3

This profile works flawlessly for my setup.

This information would have been nice for myself to have when I was starting out with rockbox and osx. Hopefully this will help some of you get setup with a sweet workflow for keeping your music synced. 