---
layout: post
title:  "Let's GO Girls - Learning Go Fundamentals"
permalink: /learning-go-fundamentals/
date:   '2026-05-05'
categories: home blog
excerpt: "I've been coding for 10+ years and finally decided to learn the core back-end fundamentals. Instead of leaning on tutorials (or AI) to coast through another language, I forced myself to start from zero with Go, facing fear of the unknown. Pointers broke my brain, “simple” CLI tools turned into real architecture decisions, and I realized I was going to challenge everything I knew about software engineering. This is the story of how a basic to-do app exposed my knowledge gaps—and why I'm finally fixing them."
---
I've been a software engineer for over a decade. I've followed the engineering way of learning for a long time now: Learn just enough on the job to do the job. In doing so, I've missed out on learning core fundamentals. I decided that if I wanted to level up my backend skills, that approach would not cut it. Why? Because every time I finish a tutorial, I have the same question: Do I actually understand this, or did I just follow along? With Go, I refuse to repeat this mistake. As a result, here we are at week 1.

## Starting Out
How do you start learning a new language in 2026? AI? No. I worked through A Tour of Go. I finished every lesson except concurrency: we're saving that for week 5. I wanted to focus on the fundamentals before adding complexity.
Pointers, especially, took longer than I expected. Not because the concept is impossible, but because I'm not used to thinking about data this way. When your baseline is JavaScript/TypeScript, you don't usually think in terms of memory addresses. Go forces you to. The traditional Google search resulted in explanations that still flew over my head. This is where I used AI. Claude helped explain pointers in a way that made sense for my JavaScript brain. But we'll talk more about this later. It's time to dive into what I built and my process.

## Phase 1 Project: CLI To-Do List
When I worked with Claude to develop a lesson plan, I made sure to include a weekly project that reinforced what I learned that week. This week's project is a CLI to-do list that outputs tasks as a formatted table. Not impressive on the surface, but it forced me to use the core pieces I just learned, such as printing to the terminal, data structuring, and formatting the output. Before writing code, I stopped and broke the problem down:
- How does data get in?
- Where does it live?
- How do I read and transform it?
- How does it get displayed?

That became my action plan: output → persistence → commands → refinement.

## Building the CLI
I started with the smallest possible win. Created a module. Printed `Hello World.` It's basic, but it matters. I went from reading Go to running Go. Next, I wrote a single string to a text file. Then read it back. Then printed it. That loop was the first success, the first time I felt like I grasped the tutorial.
Now, the CLI: I considered using Cobra, but decided not to. I want to learn Go fundamentals, and Cobra seemed antithetical to this. I'm glad I know it exists, but flags felt more fundamental and more aligned to the purpose of the project. More importantly, I didn't want to hide behind a library before I understood what it was abstracting. So I stuck with the standard library.

### Commands and Flags
First goal: read from the file and print tasks. I implemented a basic `get` command that read from a JSON file and listed the tasks. Simple, but I had to make sure the pipeline worked. I followed by adding CLI flags, which helped with handling commands like add and delete. This allowed me to shape logic around user input. But what if no flags were passed in? Default state to the rescue, which meant a refactor from if statements to a switch. This change made the code feel more intentional, easier to read, and easier to extend. With add, delete, and list built, one last requirement to finish.

### Filtering and Structure
This is where things got more interesting. The assignment indicated I needed to filter tasks by completion status. But our current data structure didn't support this. I added a taskStatus to my data structure. That one change shifted the data model from "a list of strings" to something more structured. Now I had to update our `get` logic to allow for filtering. I created an additional list function that supports a filter parameter, then updated my switch statement to look for the flag. This was one of the first moments where design decisions started to matter. Not just "does it work," but "how should this be structured so I don't hate it later?" 

## Wrap-up
I finished the project and learned a lot in my first week. Most importantly: pointers. This was the hardest part. I learned that a pointer holds the memory address of a value, `&` gives you that address, and `*` lets you dereference it (get the value). It's one of those things that sounds simple after you get it, but getting there took me some time. The shift is subtle but important: you're not always passing values around. Sometimes you're passing access to those values. Next up was range. Range feels like an insignificant part of any language, but it is actually an upgrade over traditional for loops. It iterates in a way that's clean and readable without hiding what's happening. Finally, I learned a lot about formatting. The fmt package does more than I expected, and formatting tools like gofmt (and stricter ones like gofumpt) make a bigger difference than I thought. You stop thinking about style decisions entirely.

The goal wasn't to build the best CLI to-do app. It was to apply what I learned while building something real. I can confidently say that I accomplished this goal.
