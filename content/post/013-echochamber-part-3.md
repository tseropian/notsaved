---
author: author
date: 2023-02-20T09:03:24Z
draft: false
tags:
- echochamber-ai
title:  "013: Echochamber.ai - part 3"
type: post
---

_TL;DR: I'm building a new prototype of a social media product. It's called _[_Echochamber.ai_](https://echochamber.ai/)_ and I'm documenting the process._

After a 9 months hiatus, I finally rebooted my project last December. I finished my previous contract and decided to commit to it 3 months full time focusing on finalizing a prototype and validating my hypothesis:
> Users would be interested in receiving weekly links digest from a different perspective on topics of their interest.

This is what happened:

I mostly spent December dusting the existing code and fixing bugs in the existing codebase, which I would leverage for prototyping. It was my first time off since March, so I also took some time to visit a friend in Sweden. And my family in Paris.

I caught up with [a friend](https://twitter.com/amrsobhy) during the Christmas break. We laid down the prototype's first iteration (i.e. a curated daily digest of links about startups and innovation from MENA / Africa / ASEAN the user would not have been aware of through Social media), a medium (email) and a deadline: January 18th.

So by January 18th, I would send him (and 3 other friends) an email with 5 links about _startup/tech/innovation_ they should hopefully not be aware of).

With this deadline in mind, I returned to work in early January, and this is where the fun began. Long story short, I did deliver on time but learnt a ton on the way (ain't it the purpose?)

- Finding content on Twitter using its automated API is not enough. I had to manually scrap websites and RSS feeds to find more relevant content.
- Most of the sources about the startup scene in these regions (MENA / Asia / Africa) are mainly news about funding / acquisitions / hiring events in the area. Not specifically exciting per say. Once all this is removed, there is not a lot remaining.
- A lot of the work I thought would be automated had to be manual during this first pilot phase.
- Also, scraping content using Google Cloud NLP APIs ended up being much more costly that I would have imagined. I spend almost 30£ per import of articles for 5 users. I'll let you imagine how this would not scale up. I ended up reducing this cost drastically on running some off-the-shelf model from [Hugging Face](https://huggingface.co/jonaskoenig/topic_classification_04) and running it locally (a very Frankenstein setup between my laptop and a VPS server)

I've been swearing a lot to my friend during these couple of weeks. But I delivered. You can see [the result here](https://click.echochamber.ai/mailings/4e88ac53-8f1e-43b7-ad29-3f26f106e2f1).

I wasn't happy with the result for multiple reasons: 

- Finding relevant content was challenging. I could have changed the topic to something I'm more interested in (I initially thought about switching to more sustainability-focused topics, but still).
- The feedback from the readers was OK, but not necessarily overly excited.
- Looking for more niche / long-tail content would have involved much more manual editorial content. If you want to highlight a small blog or a niche article, you need to provide more context around it, which can't be automated.
- Also, the newsletter business is overcrowded with quite massive players, and I'd struggle to get a microscopic share of their attention.

So I decided to pivot. The second hypothesis was the following: 
> Users would be interested in being immersed in more native Twitter content about topics of their interest from a different perspective.

For example, suppose you are a software engineer in your late 30s. In that case, you could be interested in receiving more Twitter native content from a software engineer in his mid-20s.
By native Twitter content, I mean web links and anything posted on the social network (photos, videos, threads) in the shape of a _dummy_ timeline (either on a webpage - or embedded in a browser extension).

I started some data collection (NDLR: it's hard to search Twitter accounts by age :-) or rather, you have to crosscheck it with another source), wrote some code, hacked some more data collection. And [this happened]( https://www.theverge.com/2023/2/2/23582615/twitter-removing-free-api-developer-apps-price-announcement).

Twitter no longer provides free access to their API (the primary source of my data). I'd have to pay (the monthly subscription was still somehow affordable, but I didn't want to give money to a company run by a lunatic). 

At this stage, being almost 2.5 months into my sprint, with minimal traction proved and my source of raw data being compromised, it was hard to continue to push in the dark.

I'm stepping back again, looking for another full-time job.

To be continued (or not).
