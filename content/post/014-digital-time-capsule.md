---
author: author
date: 2025-10-10
draft: true
title:  "014: Digital Time capsule"
type: post
---

### 1. Introduction
I have been making websites since high school in the late 90s. I learnt to write HTML code on my father's old laptop (I even retrieved the tutorial I followed). My fist page was hosted on Geocities (I sadly lost my Neighbourhood id).

I'm telling you here about a time that those under twenty cannot know. No CMS. No frameworks. No CSS. No Javascript bullshit :-) We were literally writing HTML code with notepad and uploading files one by one using FTP.

I continued at university, started to build some fan-sites for heavy metal bands I was following. That's when I also learned PHP and MySQL. Big shoutout at Free.fr (the French ISP which was providing 100Mb storage hosting with MySQL database for free - unheard of at the time). 

I then focused most of my studies projects to learn and improve my skills, to land on my first job as web developper. 


### 2. The Archaeological Dig: Technical Process
The main issue is that I lost most of my backups in a backdup drive crash in 2007 (in a pre cloud backups era). 

My most recents websites were still backuped up in a old web hosting but anything pre-2004 is definitely gone.  So for this exercise to be interesting, I would definitely have to retrieve them from the Way Back Machine. 

Finally having some time off in between jobs, I finally rolled up my sleeves. 

I used a [Ruby CLI tool](https://github.com/StrawberryMaster/wayback-machine-downloader) with a bit of [elbow grease](https://github.com/StrawberryMaster/wayback-machine-downloader?tab=readme-ov-file#ssl-certificate-errors) to get the raw files from the WBM API.

Once the downloads complete, you will have a folder with all the raw files in timestamp formatted folders. A small bash script helps you to merge all files in a singe root folder.

All your files will be named as served by the original website (in my case `filename.php?id_news=1234`, or even `index.php3?lang=1`). I will host these archives on a static hosting (likely Github Pages) so I renamed all the files in `.html` (so it can be served by the hosting) and update the links in the matching files.

I started manually but quickly got bored so but Thanks Claude Code for the work. 

UTF-8 wasn't a thing in the early 2000s so I also tried to correct as many broken special characters as possible. 

I ended up with one folder by website, which I then uploaded to a Github repo (and backed up on my NAS for posterity). That's 13 folders which you can browse in Section 5. 

### 3. What I Unearthed: Discoveries and Limitations
The process has some limitations, which I believe is linked to the scraping mechanism of the WBM. 

My very first websites were using iframe and these are not supported very well (who would have thought so)

Some pages were missing (not a lot) and some images as well (mostly the ones which were displayed in CSS, mostly the ones designed in popup in in the 2003/4 era). 

But overall, I managed to revive a substantial enough sample of my web development history, especially in my early years. K


### 4. Reflections: A Conversation with My Younger Self
Reviving these websites ended up being much more emotional than I imagined to be




le plaisir que tu as qd tu es gamin
bcp d'insouciance, tu joue par pure plaisir. Ta decouverte de la tech 
passione s
1erres mises en ligne, 1eres pression de mise en ligem 1ere, 


### 5. Experience It Yourself
These archives are [available online](http://archives.followtheway.info). 
To save you some time, I prepared a small `TL;DR;` screenshot selection.

* My 2nd website ever (after the lost Geocities mini site)
* My first fan site (Devin Townsend), 2001
* Probably one of the designs I'm the most proud to this day

### 6. For the Technically Curious: Source Code Deep Dive

