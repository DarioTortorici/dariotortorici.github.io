---
layout: post
author: Dario Tortorici
title: "Product Research Q&A"
excerpt: "Some useful questions to ask when conducting product research.<br/>"
image: /assets/images/blog_thumbnails/product_research.jpg
date: 2025-03-20
categories: 
  - Entrepreneurship
  - Product management
tags:
  - Product-research
---

# TLDR

Some useful questions (and answers) I asked myself for my side project [Glimboard](https://dariotortorici.github.io/projects/glimboard/). I think some of these questions are not only related to my product, but they are systematic questions to ask yourself when doing product research.

---
# Introduction

If this isn't the first article you've read, you know that I have a project called [Glimboard](https://dariotortorici.github.io/projects/glimboard/), an interactive platform designed to train and inspire creative minds. Today I want to go deeper into product research. I've thought about some questions that are useful to consider when implementing the right features in a product, allowing it to be planned and designed properly. Then I will give my answer for my project.

> Sometime questions are more important than answers
> — Nancy WIllard

If you like this post, I will also map out the other phases of product management. Of course, I welcome suggestions on the questions themselves and different answers. In short, don’t hesitate to write to me!

# Q&A

I have divided the questions into different topics. Feel free to jump to the section that interests you the most.

## Core Problem and Target Users

**Q: Who is the primary audience? Professionals looking to enhance creative thinking, students, or a broader audience?**

It could only be the first question.

> As a product manager, you’ll be the advocate for the customer.
> — Gayle Laakmann McDowell

A: The primary users are professionals who want to improve their creative thinking, at least in the beginning. Then it would be good and beneficial (socially and economically for the platform) to reach a wider audience.

---

**Q: What are the main pain points? Are users struggling with creative blocks, lacking confidence in their ideas, or simply looking for structured ways to improve creative thinking?**

A: The pain points are different depending on the customer's profession. I could write a whole article about that. In general, we want to provide a solution for those who are simply looking for structured ways to improve their creative thinking. This is common in any creative profession. I also want to address other pain points of specific professions, but it is well known that prioritizing is a critical skill for a PM, so for now I will focus on the core.

---

**Q: What types of creativity? Artistic creativity, problem-solving, or innovation in business and tech?**

A: Similar answer as above. Initially, I'm tackling artistic creativity. Later we'll expand into other areas if it's feasible.

## Core Use Cases and Goals

**Q: Why would a professional use GlimBoard?**

A:  There are many professionals looking for daily creative workouts, brainstorming tools or exercises to overcome creative blocks. Contact me for more information on market analysis.

---

**Q: What drives professionals to engage in creative training? What might prevent them from consistently using GlimBoard?**

A: Professionals recognize creativity as a competitive advantage. Many invest in creative training for differentiation and continuous learning. However, time constraints and skepticism about the tangible impact of creative training are significant barriers.

---

**Q: How does GlimBoard fit into their day/existing workflow?**

A: The plan is to build a standalone tool first. Later I want to integrate it with other creative processes and tools that people already use. The mix of tools and games is crucial because I want to emphasise the fact that creativity is fun, that we can work with it, play with it and why not do both together.

---

**Q: What kind of engagement do you expect? Should the platform be used in short bursts (e.g. 5-10 min sessions) or for longer periods of time?**

A: I think the platform will be used in short bursts to complete games, then post and watch some feed posts.

---

**Q: How do we measure success?**

A: What would indicate that users are genuinely improving their creative thinking is a great question. The creativity is difficult to assess. Success can be measured through self-assessments, peer reviews, and AI-generated insights on creativity (evaluating novelty and usefulness).

## Feature Design

### Mini-Games Mechanics

**Q: What kind of exercises should we include?**

There are plenty of exercises that can be implemented. Here some examples.
For writers and copywriters:

- Come up with 5 solutions to a given problem
- Connect 5 dice images into a story
- Fill in a missing paragraph of a story
- Invent a meaning for a non-existent word

For artists:

- Transform a random doodle into a finished drawing
- Draw a character based on a description
- Express a concept in one drawing (like a Rorschach test)

For designers:

- A game to match and experiment with color combinations

---

**Q: Should the difficulty adapt based on user progress?**

A: No difficulty adjustment planned. Could be an idea, but judging creativity is difficult and having an unfair system is far from what I want. A roadmap of unlocking exercises could be implemented, but I don't see the benefit of implementing it at the moment.

---

**Q: How do we create a habit-forming experience? What triggers will bring users back?**

A: This is important. While the goal of the platform is not to suck up your attention, in today's attention-seeking system, we are competing with every other service out there. Implementing a streak system (like Duolingo) and social engagement features, like group exercises, could be the key to take our space.

### Social & Peer Review System

**Q: Should users be able to comment, vote, or provide structured feedback?**

A: This is tricky. I can imagine a scenario where someone who is really proud of their work is faced with the harsh reality of comments. Creativity, like humor, is a matter of taste. Implementing only a voting system with emoticons can preserve the fragility of the users. I'd like constructive feedbacks, though, so maybe there's room for comments in some of the more structured exercises.

### AI Evaluation System

**Q: Should AI provide real-time feedback or periodic insights?**

A: As I've said before, creativity is difficult to assess. For this reason, AI evaluation should not be the primary method of evaluation. This would also avoid large costs in scaling. It should provide periodic insights, perhaps a weekly report might be useful.

---

**Q: How do we ensure the AI understands diverse creative expressions?**

A: This remains an open question that needs to be explored further. The implementation of this AI could also be a paper, but is certainly a dedicated post here.

## User Experience Flow

### Onboarding

**Q: What are the key moments where users drop off, and how do we prevent that?**

A: This is a common question. A smooth onboarding process is a must everywhere. I'm also thinking about a gamified sign-up process that makes users feel creative within the first 2 minutes. This will be helpful to personalize user experience by their profession and preferred exercises.
Another key scenario is when streak breaks. For that, I will implement a streak recovery mechanism. Having broke the streak can be discouraging, having a way to save it keeps the user with a purpose.

---

### Daily Engagement Loop

**Q: How do we motivate users to return?**

A: User retention will be improved by implementing daily challenges, streaks and group challenges.

### AI Insights and Progress Tracking

**Q: Should users see a dashboard of their progress? How do we balance structured feedback with keeping the experience fun?**

A: At the moment, I think would be beneficial visualize the AI as a insights provider on individual responses rather than overall progresses. This is due to implementation difficulties

## MVP

**Q: Should we launch as a web app, mobile app, or both? Do we need accounts, or can users start playing immediately?**

A: Launching both as a web and mobile app using React. No account is required to play, but an account is needed to post content.

---

**Q: What are the key features of Glimboard that I want to showcase in the MVP?**

A: Cutting out non-essential features to get to the core of the product is not easy when you are talking about "social networks". Of course the platform isn't intended to be a traditional social network, but I think the core of the product is peer review. A social network has to deal with a lot of edge cases (e.g. message spam).
Combined with the product concept of the [1st version of Duolingo](https://dariotortorici.github.io/blog/duolingo-handbook/), the MVP will take a lot of time. Talking about other features, of course, some games and tools. To start to understand how much is the contribution of both.

---

**Q: Which mini-games and tools should be included in the first release?**

A: The MVP should offer variety from the start, to test interest of different professions.
I was thinking about these exercises:

- Come up with 5 solutions to a given problem
- Connect 5 dice images into a story
- Invent a meaning for a non-existent word
- Invent the name for a color
- Provide a question to an answer

and tools:

- Palette generator
- Brainstorming listing

---

**Q: Should the emoji-based voting system be in the MVP, or can it come later? Is AI evaluation necessary at launch, or can we start with just peer reviews?**

A: Start with emojis and peer reviews, without AI evaluation. Otherwise you will never see the project.

---

Image Credits: UX Indonesia (Unsplash)
