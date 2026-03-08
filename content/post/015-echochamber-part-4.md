---
author: author
date: 2026-03-02
published: false
tags:
- echochamber.ai
title:  "015: Echochamber.ai (part 4)"
type: post
---

_TL;DR: I'm building a new prototype of a ~~social media~~ news consumption product. It's called _[_Echochamber.ai_](https://echochamber.ai/)_ and I'm documenting the process._

I left you about 3 years ago after another failed reboot of Echochamber. the After a 9 months hiatus, I finally rebooted my project last December. I finished my previous contract and decided to commit to it 3 months full time focusing on finalizing a prototype and validating my hypothesis:
> Users would be interested in receiving weekly links digest from a different perspective on topics of their interest.

## 0. The context: the concept and failed attempts.

I am still stuck with my old idea of bursting your echochamber Original idea, more relevant
Some failed experiment, lack of time 
Learned to make some chrome extension at daywork

## 1. The spark
Fast forward early september 2025. I just lost my job and looking to tinker on a new side project.
At the same time, I went to a meetup in London about Javascript and AI. Boring and poor presentation. 
Kicked me out and gave me the itch of trying to build a side project I could be proud enough for: 
1. sharing it with my friends
2. sharing it on some public community (slack or whatsapp)
3. (bonus) think of a talk which should be better than the ones I just saw

Also it would get me to learn some of the AI programming fundamentals I'm somehow missing. 




I soon found a fixed term contract so I decided to go all in vibe coding  and leverage as much possible as Claude.

Life took a its toll back, could not commit as much time as I wanted per day but I managed to send a demo to a couple of friends last week. 

- **EBackend: Node.js + Express + TypeScript** because it's boring in the best way — well-understood, massive ecosystem, easy to reason about. Controller-Service pattern keeps things clean: controllers handle HTTP, services own business logic.

- **PostgreSQL with pgvector** instead of a dedicated vector database (Pinecone, Weaviate, etc.) — one database to manage, not two. pgvector handles cosine similarity search natively with the `<=>` operator. For our scale, it's more than fast enough and dramatically simpler to operate.


## AI: A Pluggable Multi-Provider Approach

- **Bias analysis** uses Anthropic's **Claude 3.5 Haiku** — fast (~2-3s), cheap (~$0.001/article), and surprisingly good at detecting political framing and ideological lean. Gemini available as fallback.
- **Topic extraction** defaults to **OVH's Llama 3.1 8B** — 100x cheaper than Claude ($0.00018 vs $0.0075 per article) for a task that doesn't need frontier intelligence. Extracts themes and generates Wikipedia verification links.
- **Factory pattern** for both — swap providers via a single environment variable. No code changes needed. This came in handy when API rate limits hit or when testing cost tradeoffs.

## Embeddings: Self-Hosted Python + sentence-transformers

- **sentence-transformers/all-MiniLM-L6-v2** running on a simple Flask server — no API rate limits, no per-request costs after initial setup, runs fine on CPU.
- Why not OpenAI embeddings? Reliability and cost. A local service with exponential backoff retry is more predictable than depending on an external API for every article ingestion.
- Text preprocessing pipeline: Unicode normalization, control character removal, 8000-char truncation before embedding.

## Chrome Extension: React + Vite + Manifest V3

- **Vite** for the extension build — fast HMR during development, and bundle size control matters when Chrome Web Store reviewers look at your code.
- **Manifest V3** for both Chrome and Firefox from a single codebase — `webextension-polyfill` abstracts the API differences, separate manifest files handle browser-specific config.
- **@mozilla/readability** for content extraction — the same library powering Firefox Reader View. Battle-tested on messy real-world HTML.
- **Architecture:** Popup (React UI) communicates with a background service worker (handles auth + API proxy) and content scripts (page extraction + feedback widget injection).
- **Auth:** Device registration on install generates a CUID session token stored in `chrome.storage.local` — stateless Bearer token auth, no cookies, works cleanly with the extension security model.


- **Astro** for the marketing site — ships zero JavaScript by default. For a landing page, that's exactly right. Fast, SEO-friendly, minimal maintenance.
