---
layout: post
title:  "Ready to Golang - My First Go API"
permalink: /my-first-golang-endpoint/
date:   '2026-06-11'
categories: home blog
excerpt: "In Phase 2, I built a Cobra-CLI logbook as a central portfolio navigator for my Go repo, then added two algorithms — a flag-driven word frequency analyzer and a largest sum solver pulled from a real interview. The biggest lesson: arrays and slices are not the same thing in Go, and the standard library handles far more than her JavaScript instincts expected."
---
I have written APIs before. JavaScript, mostly. They worked. That has been enough.

Looking back, that is the honest summary of my pre-Go API experience: created to get the job done, lacking intentionality in the details. I knew what I was building toward, but not always why each piece was shaped the way it was. The output was the goal. The understanding was optional. Not because I didn’t want that, but because I didn’t realize I was missing out on understanding. This phase was going to change all of that. This phase was the real test of whether the plan I created for myself actually worked. I set out to build a GET API for league configurations in XFactor, and I wanted to do it differently.

## Step 1: Make a Plan

Before touching any code, I broke the work into stages. This is something Phase 1 taught me: plan first, then mock, and finally build toward real. Here is what I mapped out:

Create mock data and return it. Add Gin to convert that mock into an actual API endpoint. Add query string filtering, similar to how flags worked in Phase 1. Read from an ENV file and output those values. Then, finally, connect to Redis and replace the mock with real data.

That order mattered. Each step gave me something stable to stand on before I added complexity. I did not start with Redis because I did not want to be debugging infrastructure and application logic at the same time. I needed to lower the activation energy needed to start something that honestly intimidated me.

## Step 2: Mock It Up

I followed the official Go web service tutorial with Gin at go.dev/doc/tutorial/web-service-gin. But here is the difference between who I was before this learning series and who I am now: I did not just follow the tutorial to get the output. I stopped at each piece and made sure I understood what it was doing and why. That slowed me down, but it was worth it.

Once the mock returned, I added query-string filtering to let callers narrow the results. The pattern felt familiar from the flag work in Phase 1, which was a small but satisfying connection. Relying on what I've learned means I’m using the plan I created and that the learnings have stuck.

## Step 3: Reading from ENV

I knew I would eventually need environment variables to connect to Redis. So before I got there, I wired up ENV reading first. I chose github.com/joho/godotenv because the repo is actively maintained and well-supported. It also ties naturally into the os module, which I had already used in Phase 1. This was not a blind choice. It was a deliberate one, based on what I already knew and trusted. Small decisions like this are starting to feel less arbitrary the more intentionally I make them.

## Step 4: Redis or Not, Here I Come

This was the hard and scary part. We use Upstash for Redis in XFactor, and getting a successful ping out of it took roughly as long as everything else I had built to this point combined. That ratio was humbling and instructive. Infrastructure friction is real, and you cannot always code your way around it. Sometimes you just have to sit in it.

Once the connection was stable, I deliberately chose to stick with a zero cursor for now. We have limited data at this stage, so full pagination felt like premature complexity. I first used SCAN to support query string filtering, then pulled individual league configuration data via JSON.GET command. The sequencing mattered: scan to find the right keys, then fetch the actual content. After a bunch of trial and error, it worked. The real data came back where the mock data used to be. That moment still does not get old.

## What's Next

Ok, I built an API endpoint. Am I done? No way. When looking at the code, there is clear room to grow this endpoint. Cursor support for larger datasets. Pagination of results. Better error handling at the Redis layer.

But I am not going there yet. Next week, I am writing tests for this endpoint and want to do so before iterating on the implementation. Tests first, then expansion. That is the plan.