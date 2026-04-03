---
title: 'Chat Codex'
date: 2026-04-01T13:37:47-04:00
draft: false
categories:
  - AI LLM's
  - Web Development
tags:
  - Chat
  - OpenAI
  - Codex
description: 'The Joy of using Chat and Codex in combination creating web apps'
post: 'codex'
---

![coding](/image/coding-setup.png)

# The Joy of Building TinyNotes --- A More Human Story of AI-Assisted Development

I didn't set out to build something complicated.

In fact, TinyNotes is about as simple as it gets --- a small notes app
built with Next.js, SQLite, and a clean server-first approach.

But what made this project interesting wasn't the app itself.

It was *how it came together*.

------------------------------------------------------------------------

## It Started With a Course... and a Friction Point

Like a lot of people exploring AI-assisted coding, I started with a
course --- Maximilian Schwarzmüller's *"Codex - The Practical Guide."*

It's a solid course. Practical, hands-on, and grounded in real
development.

But I ran into something I think many people quietly experience:

> When AI is involved, following along doesn't always produce the same
> results.

Prompts vary. Outputs drift. Small differences compound.

So instead of trying to match the course step-for-step, I made a
decision:

I'd take the *idea*... and build it my own way.

------------------------------------------------------------------------

## Slowing Down to Speed Up

The first real shift was this:

I stopped trying to generate code immediately.

Instead, I worked with ChatGPT to: - Rewrite the spec - Clarify what the
app should do - Break everything into phases

That gave me three simple but powerful files:

-   **SPEC.md** --- what the app is
-   **PLANS.md** --- how to build it
-   **AGENTS.md** --- how Codex should behave

At that moment, nothing was built yet.

But everything was clearer.

------------------------------------------------------------------------

## The Environment (and a Small Reality Check)

I moved between a few machines:

-   Mac Mini (briefly... and uncomfortably)
-   Windows desktop (powerful, but friction with permissions)
-   Ubuntu laptop (older... but stable)

I landed on Ubuntu.

And honestly, that made sense.

Because at the end of the day: - Most web servers run Linux - Most
production environments *feel* like Linux

So building there just simplified everything.

------------------------------------------------------------------------

## The Rhythm That Emerged

What surprised me most was how naturally a rhythm formed between ChatGPT
and Codex.

It wasn't chaotic. It wasn't random.

It became structured.

### ChatGPT became the planner:

-   Breaking work into phases
-   Writing clear prompts
-   Helping reason through issues

### Codex became the builder:

-   Executing instructions
-   Writing code
-   Filling in implementation details

I wasn't replacing myself --- I was orchestrating.

------------------------------------------------------------------------

## Phase 1 --- Just Get It Running

The goal here wasn't elegance.

It was **momentum**.

-   Create the Next.js app
-   Set up routing
-   Add a basic layout
-   Make sure the dev server actually runs

That last point sounds obvious.

It isn't.

In my first attempt, I didn't test early enough --- and paid for it
later.

So I adjusted:

> Phase 1 ends only when the app runs cleanly.

That one decision saved a lot of frustration down the line.

------------------------------------------------------------------------

## Phase 2 --- Make It Real

This is where TinyNotes stopped being an idea and became an application.

-   Added SQLite
-   Defined a simple notes table
-   Created server-side functions
-   Hooked up basic create/read functionality

No over-engineering.

No unnecessary abstractions.

Just: - Server components for reads - Server actions for writes

And suddenly... data was flowing.

That moment matters.

Because once your app is *alive*, everything else becomes easier.

------------------------------------------------------------------------

## The Mistake That Changed the Process

Originally, I pushed too far before testing.

By Phase 3, things broke --- and I didn't want to untangle it.

So I reset.

Not the project --- the **process**.

I moved validation earlier.

Smaller phases. Faster feedback.

And everything got smoother.

------------------------------------------------------------------------

## What This Really Taught Me

TinyNotes is simple.

But the lessons weren't.

### 1. AI needs structure

If you don't guide it, it drifts.

### 2. Smaller steps beat big leaps

Breaking work into phases made everything predictable.

### 3. Early testing is everything

Catching issues early prevents rebuilds.

### 4. You're still the developer

AI helps --- but direction comes from you.

------------------------------------------------------------------------

## Where This Goes Next

TinyNotes isn't "done."

Next steps include: - UI refinement - Authentication - Deployment to a
home server - Backup strategy

But the foundation is solid.

And more importantly --- repeatable.

------------------------------------------------------------------------

## Final Thought

This project wasn't about building a notes app.

It was about learning how to build *with AI in a way that actually
works*.

And that, more than anything, is what made it worth doing.