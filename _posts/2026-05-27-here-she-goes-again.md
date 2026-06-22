---
layout: post
title:  "Here She Go(lang)es again - Algorithms in Go"
permalink: /algorithms-in-go/
date:   '2026-05-19'
categories: home blog
excerpt: "In Phase 2, I built a Cobra-CLI logbook as a central portfolio navigator for my Go repo, then added two algorithms — a flag-driven word frequency analyzer and a largest sum solver pulled from a real interview. The biggest lesson: arrays and slices are not the same thing in Go, and the standard library handles far more than her JavaScript instincts expected."
---
Phase 2’s goal wasn't just to write more Go. The goal was to build something that made the learning process easier to navigate, and then to reinforce what I learned by writing algorithms that applied those skills.

## The Logbook
Before writing anything new, I decided to build a logbook. Why? I wanted a quick way to see every Go module I built in the repo and execute from one place. Essentially, this would be my portfolio of the work I’ve done through this learning process.

To build it, I added Cobra-CLI. I avoided Cobra in week 1 because I wanted to understand the fundamentals around flagging before I used it. Now that I had the foundations under my belt, week 2 felt like the right time to introduce it. I can explain what my code did and why.

Currently, the logbook only executes week 1 modules. Week 2 appears in the list, but there’s no reason it should be executable. The logbook itself is the week 2 deliverable, so running it would be circular. It forced me to think about the interface before the implementation.

## Expanding the Repo: Two New Algorithms
Continuing with phase 2 of the curriculum meant focusing on algorithms. I added two more algorithms to the project.

### Most Occurring Word
This module started as a straightforward problem: find the most occurring word in a string. The first step was to create a simple module that took in one parameter: a string. Running the module with the string outputted the most occurring word. Further, what if I wanted the least-occurring word, or simply a count of how many times a word occurred? I explored this with flags, and the final version was born. One algorithm, three behaviors, all driven by flags. This approach felt familiar because I used a similar flag-based pattern in week 1's CLI to-do list — but applying it to string analysis made the pattern click in a new way.

### Largest Sum
During an interview, I received the following problem: Given a list of numbers, what is the largest possible sum, and which numbers make it up? Usually, after an interview, I store that knowledge away. This time, the lightbulb lit, and I was off to implement this in Go. This implementation pushed me into lists and sublists — or as Go calls them, slices. That distinction matters more than I expected. My biggest challenge coming from JavaScript was passing in a list and not thinking of it the same way I thought of arrays. I couldn’t pass a list in a flag the traditional way, so I had to pass a string, parse it, and convert it into a list.

## Phase 2 Learnings
My biggest takeaway from this phase was that arrays and slices are not the same thing in Go. In JavaScript, an array is just an array. It’s a flexible, dynamically sized list you don't think twice about. But in Go, arrays have a fixed length. Slices are the flexible version, but they're built on top of arrays and behave differently in ways that actually matter: how we pass lists, how we duplicate lists, and how modifications propagate. I’m still trying to internalize this concept, but it was a great lesson.
String analysis, on the other hand, is simpler in Go than I expected. The standard library handles a lot. No reaching for lodash or third-party utilities — the `strings` package covers most of what you need cleanly.
Ranges are still preferable to traditional for loops when you're iterating over a collection. I noted this in week 1, and it keeps proving true. Go's range keeps iteration readable without hiding what's actually happening.
And that brings me to the broader takeaway: Go's built-in packages are more capable than I thought a language would provide without external additions. My instinct, coming from a JavaScript background, is to look for a library immediately. In Go, that instinct fires too early. The standard library is the right first stop more often than not.
I’ve completed phase 2. The repo is starting to feel like a real system and portfolio — not just a collection of exercises, but something I actually want to open and share with others.