---
layout: post
title:  "Vibe Coding as a Senior Software Engineer: Lessons from Building a Custom Lifting App"
permalink: /vibecoding-review/
date:   '2026-10-19'
categories: works
excerpt: 'Frustrated by lifting apps that lacked personality and flexibility and kept core features behind expensive subscriptions, a beginner lifter who works as a software engineer decided to build their own workout tracker that could grow with their fitness journey. The project was also a chance to test "vibe coding" on a real-world project as a senior engineer and see what it can and cannot do.'
---
For a long time, I've wanted to start lifting weights, but I've always struggled to actually get started. As a software engineer, my first instinct was to find an app to track my workouts and progress. However, as I browsed existing options, I ran into a common set of frustrating issues: most lifting apps lacked personality and customization, were inflexible, and locked core features behind steep subscription paywalls. For someone just starting out, this experience felt neither approachable nor encouraging.

Instead of settling for a subpar solution, I decided to build my own app—one designed specifically to grow with me as my fitness journey evolved. But beyond solving my workout-tracking problem, this presented an exciting opportunity: as a senior software engineer, I wanted to test "vibe coding" in a real-world scenario and analyze its capabilities and limitations.

## What is Vibe Coding?
For those who may not know, "vibe coding" is a workflow in which software development is primarily guided by natural-language prompts using AI tools. This approach lets engineers quickly generate, iterate, and refine code by expressing intent rather than typing every line. Examples of vibe coding include using AI coding assistants through command-line interfaces (CLI), mobile applications, or integrated development environments (IDEs) to prototype full features on the fly.

## The Pros: Unmatched Speed and Continuous Learning
One of vibe coding's clearest advantages is the speed of rapid prototyping and iteration. It excels at wireframing and building interactive mockups almost instantly. This speed creates a remarkably fluid feedback loop, perfect for wireframing and proofs of concept. Unsure if something can be built? Vibe code it. Working with a designer to test a flow? Vibe code it. Want to test a different design that only moves components around? Vibe code it.

While lifting at the gym and using my app, I would occasionally encounter minor UI friction points or think of useful feature improvements. Instead of waiting until I got back to my desk, I'd finish my workout, grab a drink, and use an AI assistant to implement the fix or feature directly from my phone. By the time I left, the update was live and ready for my next workout.

Vibe coding is also an incredible educational tool. It lets you describe a high-level problem and immediately get viable architectural options. It teaches relevant technical vocabulary, expands your skillset, and introduces modern techniques or libraries you might not have considered.

## The Cons: Context Drift, Technical Debt, and Required Expertise
Despite its strengths, vibe coding is far from perfect. One significant drawback is that the AI sometimes overlooks project constraints. Throughout development, I repeatedly had to remind the model to stick to our existing design system rather than invent new font sizes, spacing, or UI components.

Furthermore, the initial code structure AI assistants generate is mediocre at best. During the initial build, the model dumped almost all application logic into just a few massive React files. Instead of proactively suggesting component modularity, it regularly duplicated code across the codebase. When asked for new features, it often wrote entirely new components from scratch rather than extending existing design system components.

Crucially, effective vibe coding heavily depends on pre-existing domain knowledge. To learn or troubleshoot effectively, you need to know what questions to ask and how to ask them. To maintain code quality, you must know how to review code properly. AI assistants rarely offer feedback, refactoring suggestions, or architectural best practices unless you explicitly prompt them. Without senior-level oversight, this workflow can easily perpetuate bad habits and technical debt.

## Conclusion
Ultimately, vibe coding is a fun, highly motivating approach that shines bright in personal projects and early-stage rapid prototyping. Removing friction and instantly seeing ideas come to life keeps momentum high. However, it isn't production-ready out of the box. Human code reviews and foundational engineering knowledge remain essential to ensure maintainable, high-quality outputs. 

As we move forward, if relying solely on vibe coding isn't enough to develop complex production software, what alternatives exist? In my next post, I'll dive deep into what I believe is the solution: Spec-Driven Development (SDD). I'll cover what it is, how it differs from vibe-coding, and how combining structured specifications with AI capabilities yields better, more robust software.
