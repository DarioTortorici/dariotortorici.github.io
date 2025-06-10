---
layout: post
title: "Code Assist vs GitHub Copilot"
excerpt: "Exploring the power of the new free Gemini Code Assist compared to the well-established GitHub Copilot.<br/>"
date: 2025-03-04
image: /assets/images/blog_thumbnails/gemini_logo.png
categories: 
  - AI
tags:
  - AI-tools
  - Programming
---

# TLDR
Exploring the power of the new free Gemini Code Assist compared to the well-established GitHub Copilot.

---

# The release

Google has once again released Gemini Code Assist for free.
This move is likely because Google is lagging in the AI coding race (I agree).

> If you're a student, here's a pro tip: GitHub Pro gives you free access to Copilot, which is still arguably the best option.

That said, Gemini Code Assist isn't just a weaker version of Copilot. As a **free alternative to Copilot and Cursor**, it actually comes with some real advantages:

- **More daily requests** (6,000 code-related queries + 240 chat interactions)
- **Larger context window** (128K tokens vs. Copilot's 64K max with GPT-4o)

One downside? **You can't choose different models.** Meanwhile, Copilot lets you switch, and as of March 2025, [Claude 3.7 Sonnet is looking like the best LLM for coding](https://www.anthropic.com/news/claude-3-7-sonnet).

There are other tools: Cursor, Tabnine, Codeium, but I haven't tested them, so I'll just remind you that they exist.

---

# My tests

## Autogenerate inline code

Both Copilot and Gemini performed well here, **almost identical**. This feature is mostly about saving time, so it's hard to do an in-depth comparison. Maybe it's placebo, but I felt Gemini with longer context performed slightly better. **Still, I'd call it a tie.**

## Bug fixes

I ran both tools on a real issue I faced in my project, Glimboard (a social network, but not really. More on that [here](https://dariotortorici.github.io/projects/glimboard/)). The codebase isn't huge, but with around 150 files, I'd still call it a sizable project.
Stack: **React + Tailwind**.

The problem: A UX/UI bug with flashcard-style **animations messing up button clicks** after a shuffle. The animation makes one card slide under another, simulating a deck shuffle. But somehow, the buttons displayed above became **unclickable in certain areas**. Debugging revealed it was due to overlapping buttons.

Both **Gemini and Copilot fixated on the wrong issue**. They kept trying to debug the **button z-index** logic instead of addressing the core problem. Truth is, I didn't fully understand the issue either, but I eventually realized the simplest fix: **just remove the bottom button after the animation.**
**The real winner? Me.**

> Here, if you are interested, is the guess of the problem. I think it was related to how the button logic is implemented in the framework I'm using. Since a button is left without focus, the cursor becomes the default. Even if you are still inside the other button. When you move again, (given that you are inside at least one of the two buttons) the hand cursor shows back.

![Button problem](https://dariotortorici.github.io/images/blog-posts/code-assist-vs-copilot/Overlap-btns.png)
*High fidelity image to explain better what I'm saying*

## New feature

Task: Add to a dice roller the possibility to lock specific dice before re-rolling.

**Gemini completely imploded**: it couldn't even handle one subtask properly, let alone the full feature. Worse, it started messing with my libraries for no reason.
**Copilot did a solid performance.** Not only did it implement the basic logic correctly, but it also added a small visual cue (a red outline) to indicate locked dice. The code wasn't perfect, some warnings popped up due to edge cases, but it worked. Point goes to Copilot.

# Conclusions

If you want to use Google Code Assistant as AI-assisted autocomplete is a productivity boost. For the fully auto-generated code? Still a mess. But honestly, this is where we are with AI coding tools. As long as these LLMs make mistakes, we still have a job, at least as debuggers. Personally, I still prefer writing my own code. Debugging "your own hallucinations" is already painful. Debugging someone else's is a nightmare.

---

Image Credits: Google
