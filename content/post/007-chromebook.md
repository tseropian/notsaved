---
published: true
date : "2017-10-16"
section :
- What I Learnt Today
- Blog
title : "007 : Chromebooks"
---
Being in-between jobs, I needed a cheap laptop to be able to work outside of my flat in my favorite South London cafes. 

I could have got a nice Macbook or the Ubuntu certified Dell XPS13 (or even a Thinkpad) but these tiny machines don't come cheap and there is a strong change that I would get a work laptop with my next job matching the same specs. So I'd rarther save a grand for a personal laptop that could get the dust in a couple of weeks. 

In a nutshell I would be basically look at the following specs: 

- an ultrabook light laptop that I can travel around with in my backpack without killing my back.
- a lightweight processor (I don't need that much  horsepower for a work station and when I do, I'd rather spin an AWS instance or a baremetal server) 
- fully functional Linux (ideally Ubuntu) I can work on my web applications (Node.js, PHP etc) 
- a Web browser 
- full HD screen (1920 x 1080) with an extra HDMI connection for dual display supported out of the box
- Less than 300£ so I don't feel guilty when the laptop will get the dust.

I had a look at the Chromebook line which would fit most of these criteria for about 300 GBP. I ended up getting the [Chromebook 14](https://www.acer.com/ac/en/GB/content/series/acerchromebook14) from Currys. 

*Mandatory geek setup* : 

- There is a bash environment officially suported on Chrome OS which you can [customize](https://gist.github.com/aaronhalford/a009bc73498407ae80e2)
- Also , there is [Chromebrew](http://skycocker.github.io/chromebrew/), a missing package manager (a la homebrew on Mac) which support a decent list of software.  
- Obviously, [Crouton](https://github.com/dnschneid/crouton) for a KDE based Ubuntu in chrooted environment for anything else than the limited possibilities above.
- [Installing Playstore on a Chromebook] (https://support.google.com/chromebook/answer/7021273), still experimental though

That's all for now.

I've been using the chromebook on a daily basis (on Ubuntu whenever I needed to do some coding work, ChromeOs otherwise) and I'm happy with it.

The only limitations I found are setting up Vagrant on Crouton. There are some workarounds but I haven't dig into them yet.

Otherwise all good.
