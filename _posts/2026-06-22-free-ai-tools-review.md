---
layout: post
title:  "72 Hours. Free AI Tools Only. Here's What Actually Happened."
permalink: /free-ai-tools-review/
date:   '2026-06-22'
categories: home blog
excerpt: "I took a break from my Go journey to try to create an app in 72 hours with only free AI tools. Let's see how far I get."
---

This post took longer to write than expected. Not because the words were hard to find. Because the feelings were. I kept drafting and deleting, drafting and deleting — trying to untangle what I expected from what I learned, while not focusing on what made me mad.
So here's what we're covering: I spent 72 hours, spread over about a week, using only free AI tools to build a web app. No paid tiers. No subscriptions. Free.
I've used AI to support my development process before, paid and free, and I've written about some of those experiences. But I'd never built anything from scratch using only free AI tooling. I needed to try to understand the landscape and the limitations. So I did, and here's what happened.

## The Ads Are Wrong
I didn't go in expecting magic. I want to be clear about that.
The claim I wanted to test was the one you've seen everywhere. The "one prompt and your app is built" narrative that's been running on every social media platform for the last two years. I had a healthy skepticism going in. I'm a senior engineer, and I've watched these tools closely. I wasn’t expecting a miracle. I was, however, curious whether I was being too cynical.
Unless you have a meticulous requirements document written ahead of time — and I mean meticulous, down to the data model, the component structure, the API contract — and you know exactly how to phrase each stage of development, you will not get a working app doing everything you want from a single prompt. You just won't.
72 hours later, I have three pages built. The UI is rough by my professional standards. The codebase is messy. And it still took me multiple passes, multiple course corrections, and no small amount of manual cleanup.
What I do have is a working app using React, Go, SQLite, Docker that is up and running, plus a few TypeScript web scrapers that load initial data. But let's be real about what 72 hours actually produced. That's not the story the ads are telling. No production-ready app. No beautiful website. A few pages, endpoints, Google login, and web scrapers. I haven’t even checked for security around login, but I’m sure there are vulnerabilities.

## The Constraints Are Real
Free tier is not just "a little slower." Free tier is a wall you will hit repeatedly. I used my entire monthly Copilot allotment on app setup. Setup. By the time I was ready to iterate, I was already out of options with Copilot. Same story with Figma Make. I barely got through a first pass at a UI before I hit the ceiling. What should have been a creative exploration turned into a sigh, leaving disappointment.
And it cascades. You run out of credits. You drop to a lower-quality model. The responses shift. The suggestions get less precise. You feel it, even if you can't always name exactly what changed.
There were sessions where I had to split development between Claude and ChatGPT because I'd burned through credits on one and needed to keep going. That means reintroducing context, that some decisions don't carry forward. And consistency becomes a gamble — not because the tools are bad at reasoning, but because they don't always remember what they decided three conversations ago. That's not a small thing. Codebases have opinions baked in. When the tool doesn't remember its own opinions, you inherit the inconsistency.

## But It's Not All Negative
Here's where I have to be honest in the other direction.
I get it now — why people say AI made us all system designers. Every iteration pushed me to understand and articulate why I was making a decision, not just make it. What should this component own? Where does the state live? Why does this data shape make sense here? The tool asked, implicitly, by generating something that wasn't quite right, and I had to name the gap.
That started during my Go learning journey, but seeing it happen in the frontend, which is my home turf, was something else. I can now express many of my engineering decisions in ways I never had to before. Why I prefer styles in external CSS files rather than inline styles with React and CSS properties, for example. I've known that preference for years. I haven't always been able to explain it cleanly, but now I can.
Debugging is also consistently good, even on the free tier and on a lower model. The quality drop on generation is real; the quality drop on explanation is much less so.
And the explanations when you ask, such as when you just say "why did you do it this way, help me understand", are still excellent and without ego. The responses are genuinely useful, which isn’t always the case in places on the internet. I was glad to learn that behavior doesn't go away with the free tier.
The tool is also good when the scope is small. A single component. Wiring a component up to an API. Diagnosing one weird bug. Constrained, focused problems get good results.

## Final Thoughts?
Free AI tools are useful. They're a good place to start learning. They will help you better understand your own decisions. They will explain things without judgment. They will get you unstuck on small problems faster than a Stack Overflow rabbit hole.
They will not replace engineers. Not soon.
And the "tools are only as smart as the person using them" thing is real, but I want to expand on that framing a little. This framing places all the responsibility on the user and none on the systems marketed as accessible and easy. If you need deep expertise to get good results, then the tool is not as democratizing as advertised. You will still need to hire a professional.
That matters, especially for learners. Not everyone can spend $20 a month to access a single tool at full capacity. The barrier to entry is higher than the ads suggest. And the gap between the free tier and the paid tier is significant enough that someone learning on the free tier might walk away with an incomplete picture of what these tools actually are.
We should say that clearly. I'd rather say it than pretend the playing field is flat. Genuinely. I will recommend using them when and where possible. Not because they are exceptional, but because we need to understand what entry to the field looks like now. Understanding the limitations enables us to empathize in this quickly changing environment. In the end, companies and hiring managers can’t expect mid-level engineers to have experience with the latest versions of AI tools, especially when there’s a price tag attached.