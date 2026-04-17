---
published: false
date: 2026-03-02
title: "015: Echochamber.ai (part 4)"
---
*TL;DR: I'm building a new prototype of a ~~social media~~ news consumption product. It's called [Echochamber.ai](https://echochamber.ai/) and I'm documenting the process.*

## 0. The context: the concept and failed attempts.

I left you about 3 years ago after (yet) another failed reboot of [Echochamber.ai](http://Echochamber.ai). I am still focused on the same idea; 

> Users would be interested in receiving links digest from a different perspective on topics of their interest.

In a time where the media consumption is still more polarized, I am convinced the idea is somehow relevant. I was trying to commit to dedicating some time to run a couple of small failed experiments but without success. 

In a complete unrelated point, I was learning to build Chrome extension during my day work. 

## 1. The spark

Fast forward early September 2025. I just lost my job and looking to tinker on a new side project to keep my crafting software skills sharp.  
At the same time, I went to a meetup in London about JavaScript and AI. One of the talks (about building an AI agent using Typescript) was so boring and poorly presented that it gave me a spark.     
It kicked me out and gave me the itch of trying to build a side project I could be proud enough for: 

1. sharing it with my friends
2. sharing it on some public community (slack or whatsapp)
3. (bonus) think of a talk which should be better than the ones I just saw

Also it would get me to learn some of the AI programming fundamentals I'm somehow missing. 

I soon found a fixed term contract so I decided to go all in vibe coding  and leverage as much possible as Claude Code.

## 2. The scope of work

My plan is to combine what I already know (building back-end applications and scraping data, building browser  extension) and pair this with AI so I can start getting my hands dirty with some of AI relates technologies.

More specifically, I want to : 

- Parse the article being read with a browser extension
- Extract content and send it to a back-end
- Analyse the bias of the current article and its topics
- Based on the current article bias, send an article about the same topic  from a different bias.

Easy enough should be. 

## 3. The tech stack

- The Broweser extension is using React. 
- The backend is using Node.js + Express + Typescript (because it's boring in the best way and I understand quite well). 
- Datastore is using **PostgreSQL with pgvector** instead of a dedicated vector database (Pinecone, Weaviate, etc.) 
- AI Content analysis: I built a pluggable Multi-Provider approach so I swap providers via a single environment variable. At the moment the bias analysis is handled by Mistral, approvimatively 50x cheaper than Claude. 
- Topics embedding runs on Transformers, Hugging face abstraction layer running on a simple Flask server 

## 4. The sprint

Life took a its toll back, could not commit as much time as I wanted per day but I managed to send a demo to a couple of friends last week. 

## 5. The next steps

