+++
title = "011: Echochamber.ai (part 1)"
date = "2022-04-15"
published = true
tags = ['echochamber-ai']
+++

_TL;DR: I'm building a new prototype of a social media product. It's called _[_Echochamber.ai_](https://echochamber.ai/)_._

I've started to document the process here.

From the about page:

> [Echochamber.ai](https://echochamber.ai) is an anti-echo-chamber tool. First, we identify your topics of interest based on your Twitter profile and the accounts you follow. Then, we will send you a daily digest of 5 news based on relevant issues for you outside of your social media bubble.

## Week 0: the context

- I tried (and failed) to start a tech startup in 2020. I have been accepted in a founder programme called [Antler](https://antler.co/) in March 2020 (just before Covid, good timing). Looking at this experience in retrospect, I would have done things way differently (but that’s a story for another time). After moving back to consulting for almost a year, I decided in early 2021 to start [some (two) side projects](https://notsaved.org/2022/01/01/010-on-side-projects/) to get back in the habit of creating things for myself.
- Fast forward to early 2022. I was slightly drained from another year of non-stop contracting. Covid was still here (right during the Omicron wave), so I could not still travel the world (I was also waiting for my new passport). Rather than looking for a new contract, I decided to dedicate a whole month (of February 2022) to building something new.
- I've worked a big chunk of my career for a non-profit organisation focused on content and online news publications in developing countries. Most of my work there supported news players from hostile environments, especially those outside the main content distribution channel. When looking for new ideas, I naturally came back to the long tail or content distribution and how to reach some of the edge cases.
- While it's one of the most overcrowded markets, social media is still an accessible business to step in. There's plenty of data available for free (or cheap), at least on Twitter.
- I met with [John](https://createur.com/), who helped me make the jump. One hour after I explained the idea, we both agreed on a deadline (end of Feb) and the scope of work of the prototype, and he would hold me accountable for it.


## Week 1: W/C Jan 31, designing the infrastructure

- I spent most of the first week scoping the engineering architecture or how to make a side project exciting by trying new fancy technologies.
- Shall I go full-on GraphQL, Appsync?
- Data storage: Should I go full-on NoSQL or stick to SQL database? I ended up sticking to SQL, MySQL to start with
- Shall I try Aurora serverless? It ended up being too slow, I decided to pay a premium fee for RDS
- There’s a significant natural language processing component (which I know close to nothing about). I did the first try with AWS comprehend. The results are abysmal for my limited skill set.
- I ended up trying the content analysis API from Google Cloud API, and it works almost out of the box :-)


## Week 2: W/C Feb 7

- 2 days down the line, I’m still stuck with analysis paralysis about my tech stack. Should I use a serverless backend or go full-on containerisation. Should I stick to Serverless framework or try AWS SAM?
- Thursday was a kind of wake up call. I already lost 1/3 of my 1-month sprint and haven't built anything.
- I’m deciding to switch back to an extreme KISS approach. Deploy a standard Node.js API and a set of scripts which should be able to run on my cheap server where I’m hosting most of my personal websites. Anything beyond that will wait until the prototype is validated or now.


## Week 3: W/C Feb 14: Writing code

- I’m head down into development, using simple tools (quite unusual for a side project, but at least I’m making good progress).
- By Thursday, I sent my first test email to myself (while hosting the whole stack on my laptop).
- I’m using google news RSS API to find links from a random category that the user is not following.
- By Sunday evening, I sent my first email to a real user (a former flatmate who's my guinea pig, as himself is a heavy Twitter user)


## Week 4: W/C Feb 21: First users

- I have 3 users signed up on Monday (early adopters).
- I’m sending another batch of emails to 2 users.
- One of my users told me he preferred 1 link to the other 3 I sent. I realised I have no way to track that feedback.
- On Wednesday, I'm inviting about 10 contacts, and 2 more have signed up :-)
- Finally, the ongoing situation in Ukraine does not help. Most of everyone on the planet is tweeting about it.


## Week 5: W/C Feb 28

- Sending links of random categories to users is a bit daft. I sent sports news to one of the users who does not care about sports at all. I also sent a link about a _"Troutfest"_ to a vegan user :-).
- First pivot: Rather than sending news about random categories, I want to send info from similar topics of interest to my users but from a different geographical context.
- I decided to ditch google news API (an unofficial hack from RSS) as the type of content news I was getting from that wasn't geographically accurate enough.
- After some research, I’m trying newscatcherAPI and implementing it.


## W/C 6: Mar 7

- I'm 2 weeks beyond my original time frame. I'm trying to wrap up the development so I can validate or not the prototype (i.e. continue to push the product for the upcoming months or not.
- Most of the week is spent fixing bugs of scaling my prototype code from processing content for 5 users running on my laptop to 18 users running on a server.
- After a week of debugging, I sent 5 links to my users on a Saturday morning.
- The feedback was unanimous: "They're definitely topics I wouldn't have read about otherwise, but none of them prompted me to click through to read more. I think because they weren't topics I'm interested in."
- In other words, I need to put more effort into the content curation.

So after 6 weeks, I realised that sending links that users are not aware of is easy. However, sending interesting links is much more complex and requires more fine-tuned experiments.

While I've decided to continue working on this idea, I'm stepping back. Taking a full-time contract for 6 months while working on the next iteration.

End of the 1st post, to be continued :-)

  
  

