---
categories: 
  - still-learning
  - wip
date = "2015-12-19"
tags: 
  - beer
  - "fun-facts"
title = "Still learning"
published = true
description =  null
---

Am still playing with Hugo. A couple of things I'm trying to implement.

-  ~~Continuous integration setup with Wercker.~~
-  ~~Debug theme (bullet points are missing on the homepage).~~
-  ~~Better integration with Prose.~~
-  ~~Theme based template for Hugo~~ (later).

So I have achieved the following setup. Thanks [Atchai](http://atchai.com/blog/the-cms-is-dead-long-live-hugo-wercker-proseio-and-cloudfront/#contact). Am documenting the process here so I can share it with friends.

The website you are reading is being served by a static site generator (SSG). I chose [Hugo](http://gohugo.io) as it is simple enought to be deployed on a single library (when Jekyll needs the whole RoR stack to be deployed / maintained). I'm [currently running](https://gohugo.io/overview/quickstart/) Hugo on my Macbook Pro (and I would also run it on my Windows 10 desktop, or any of my VPSes).

Obviously, sources are available on [Github](https://github.com/tseropian/notsaved) (refered as the _source_ repo).

Obviously (again), static generated files are hosted on [Github Pages](https://github.com/tseropian/tseropian.github.io) (I am using a 2nd dedicated repo, the _gh-pages_ repo, but could have used gh-pages branch for sources repo. Done so just for sake of simplicity (I just needed to add ignore the **/public** folder of Hugo in the main _source_ repository).

To make the publishing process more smoother, I've dug into continous integration (using [Wercker](http://wercker.com)). Wercker is generating the whole site at every commit on my _source_ repository, and pushing it to my _gh-pages_ repository. Here are [instructions to setup Wercker](https://www.aerobatic.com/blog/hugo-continuous-integration-with-wercker-aerobatic-and-bitbucket) and my [app](https://app.wercker.com/project/bykey/8aa5d7b97a82cf708b2b40f996ae408f) can be found there.

At this stage, any commit on the _source_ repository is visible online within less than 5 minutes completely automatically. Everyting is cloud based. No more server side machinery :-)

Finally I had a try using Prose.io as main editor for writing posts (in lieu of Github inline editor). It is doing the job but some Hugo specific features are still lacking (for example the automated generation of all meta data on run on Hugo new post/post-name). You can have a look at my prose config. Not optimized yet but I'm working on it.

The amazing thing is that most of this setup is free. I am only paying for my domain name (and could use a github.io subdomain). 

Here is my new setup. I want to continue experimenting the content as code approach and see how I can reuse some of this setup for my dayjob.

PS : The final setup step would be to enable HTTPS on github. It seems to be doable with Cloudflare. Will have a look later on. Watch this space
