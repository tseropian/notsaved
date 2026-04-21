---
published: true
date: 2026-03-02
title: "015: Echochamber.ai (part 4)"
---
*TL;DR: I’m building a new prototype of a ~~social media~~ news consumption product. It’s called [Echochamber.ai,](https://echochamber.ai/)* and I’m documenting the process.

## 0. The context: the concept and failed attempts.

I left you about 3 years ago after (yet) another failed reboot of [Echochamber.ai](http://Echochamber.ai). I am still focused on the same idea;

> Users would be interested in receiving  digest links from a different perspective on topics of their interest.

In a time when media consumption remains highly polarised, I am convinced the idea is still relevant. I was trying to commit to dedicating some time to running a couple of small failed experiments, but without success.

In a completely unrelated point, I was learning to build a Chrome extension during my day job.

## 1. The spark

Fast forward to early September 2025. I just lost my job and am looking to tinker on a new side project to keep my crafting software skills sharp.  
At the same time, I went to a meetup in London about JavaScript and AI. One of the talks (about building an AI agent using TypeScript) was so boring and poorly presented that it sparked my interest.  
It kicked me out and gave me the itch of trying to build a side project I could be proud enough of:

1. sharing it with my friends
2. sharing it on some public community (Slack or WhatsApp)
3. (bonus) think of a  presentation where I can use this project, which should be better than the ones I just saw at this JavaScript meetup.

Also, it would get me to learn some of the AI programming fundamentals I’m somehow missing.

I soon found a fixed-term contract, so I decided to go all in on vibe coding and leverage it as much as possible with Claude Code.

## 2. The scope of work

My plan is to combine what I already know (building back-end applications, scraping data, and building browser extensions) with AI to start getting my hands dirty with some AI-related technologies.

More specifically, I want to :

- Parse the article being read with a browser extension.
- Extract content and send it to a back-end.
- Analyse the bias of the current article and its topics.
- Based on the current article bias, send an article about the same topic  from a different bias.

Easy enough should be (my famous last words).

## 3. The tech stack

I ended up picking a tech stack I'm somewhat familiar with, so I can focus on levelling up in AI. The other constraint was the budget. This is a hobby project, and I want to make sure it stays within a monthly budget of < 20 GBP (a small VPS server + a couple of £ of AI credits per month).

I ended up with the following:

- The browser extension is using React.
- The back-end uses Node.js, Express, and TypeScript (because it’s boring in the best way, and I understand it quite well).
- The data store is using PostgreSQL (again, very boring).
- The topics embedding runs on Transformers, and the Hugging Face abstraction layer runs on a simple Flask server. They are stored in PostgreSQL with pgvector rather than a dedicated vector database (Pinecone, Weaviate, etc.).
- AI Content analysis: I built a pluggable Multi-Provider approach, allowing me to swap providers via a single environment variable. At the moment, the bias analysis is handled by Mistral (after I realised the hard way how expensive Claud would be). But I want to make sure I can switch to different models very easily.

## 4. The sprint

My idea was to see how much of the build can be done by using coding agents (i.e., Claude Code in this case). It ended up working well for the back-end, but the browser extension needed more manual testing. That’s clearly one of the bottlenecks in testing (i.e., I need to review changes to the browser extension manually).

Life took its toll; I couldn't commit as much time as I wanted each day, but I managed to send a demo to a couple of friends earlier this year.

## 5. The next steps

I’m now in the last 10% of the project before I can share it with the world. I’ll cover the race to the finishing line in Part 5. Watch this space.