---
layout: post
title: "The illusion of Apple's thinking"
excerpt: "Apple released a paper criticizing LLM-based reasoning (LRM) systems, claiming they don't really reason. Is it true? <br/>"
image: /assets/images/blog_thumbnails/apple_illusion.png
date: 2025-06-16
categories: 
  - AI
tags:
  - AI-research

---

# TLDR

Apple released a paper criticizing LLM-based reasoning (LRM) systems, claiming they don't really “reason” but just mimic patterns. Their research method is questionable,and in the end, the paper says more about Apple's lag in AI than about the actual state of LRMs.

---

# Introduction

Apple's recent paper on LRM models (Large-scale Reasoning Models), combining LLMs and chain-of-thought reasoning, made some noise.

I'm not going to spend time explaining what LLMs or chain-of-thought prompting are, if you landed here, you probably know the basics already.

Instead, I want to break this down into three parts:

- What does Apple actually say?
- Is it true?
- So what?

---

# What Apple Says

Apple's paper focuses on LRM models,systems that are supposed to “think” or “reason.” Apple's position is: they don't. **They're just really good at recognizing patterns.**

To make their point, they evaluated models like DeepSeek and Claude (OpenAI was excluded because it doesn't expose “thinking tokens”) on four classic puzzle games:

- Tower of Hanoi
- Checker jumping
- Blocks world
- River crossing

![Games example](/assets/images/blog_images/paper-games.png)

---

The results are surprising. At low complexity, the models perform well: they solve the puzzles and explain their reasoning. However, as the problem scales up, even slightly, **accuracy drops to zero**. This is odd because these puzzles are mechanically simple: once you understand the logic, solving larger instances is just a matter of time, not difficulty.

Apple's thesis is that we have been using the wrong benchmarks and metrics to evaluate reasoning in AI. Chain-of-thought outputs simulate reasoning, but they don't actually reflect understanding. This is because we have been rewarding models for simply getting the right answer, no matter how they get there. However, reasoning, by definition, is about the logic behind the answer. These models can solve small versions of the puzzles because they have seen them during training, not because they have understood and generalised the logic.

Therefore, Apple concludes that their findings push back the timeline for AGI. It's not just around the corner.

---

# Is Apple Right?

Let's start with this: the paper never defines what “reasoning” actually is. And that's already a problem.

Do models reason like us? No. But does that mean they _don't_ reason at all? That depends on your definition. If reasoning means “starting from premises, applying logical steps, reaching conclusions”, then yeah, **they do**. They learn it with a reward on a right answer, but guess what? So did we most of the times. Does reasoning means that it should be able to solve problems that it has never seen? Maybe, but I guess it depends on the difficulty of the problem.

So with this we connect with the second issue. Apple's benchmarks. I agree with the paper's criticism of current SOTA benchmarks. Existing evaluations can be gamed, and companies _have_ fine-tuned to score better in benchmarks before. But the decision that these four puzzle games are a solid benchmark for reasoning is completely arbitrary. Their solutions are everywhere. The solving algorithms (which _are_ the reasoning) are publicly known.

The third proble is in Apple's evaluation. These models were intentionally stripped of tools: **no code execution, no external search**. That was probably done to prove that the models can't internally derive an algorithm. But... we already know a language model can't. Removing tools just proves that it's not a symbolic math engine, which no one ever claimed. We already know that these models are the pickers of next word's probability. Tool use is _part_ of what makes LLM-based systems powerful. Cutting that out and calling it a reasoning failure feels artificial. I get Apple's side too: if it needs tools, is it really reasoning? Fair, but then we're back to the benchmark issue.

In particular, there's something fishy going on with the Tower of Hanoi results. If a model can solve the puzzle with seven disks, it should be able to extrapolate to eight. The steps are simply nested applications of the same logic. You solve the tower of seven disks in the intermediate pole, then you move the now-free eighth disk to the final pole, then you solve the tower of seven disks again. So what went wrong?

**Context window.** The solution space grows exponentially: 2^n - 1 moves. The model's memory just ran out. That's not a reasoning failure, that's a **token budget problem**. This is why the model accuracy collpases to 0.

Same goes for the multiplication analogy: I know how multiplication works, but give me two four-digit numbers and no paper, and I'll freeze too (if there are few 0 digits of course). Models weren't even given more time (extended inference), just told to "think" with basic token prediction.

I think the more reasonable test is the river crossing puzzle. Its solution length doesn't scale like Tower of Hanoi, it stays short. And yet the models still fail. So here we _do_ have a legitimate generalization problem? I guess not. While it's true that with low numbers the model was accurate because it had already seen the solution, if you don't provide the tools, you can't display the correct steps based on statistics. This can be analogously seen as the famous problem of "How many Rs are in a strawberry?". **If it cannot count, it will shoot based on the most probable outcome according to the training set.**

---

# So What?

**This paper doesn't reveal anything new.** We already knew that LLMs and, by extension, LRM models without tools are not designed to replace algebra systems. If the model fails to answer maths-related questions, does this mean that it can't reason in general, or that it is not good at reasoning about maths-related problems? If it can't figure something out that is too complex, does that mean it has no reasoning ability? All these questions collapse into the definition of reasoning. I agree with the claim that AGI is not just around the corner, but I don't know if that belief is confined to my own echo chamber or if it is widely held. Yes, we are making progress every day, but AGI is on a different level, especially given the performance plateau we are reaching as we increase model sizes. However, it is not this paper that tells us this.

What it _does_ this paper tell us is more about Apple's internal state than about its competitors. Many critics have pointed this out: this paper feels more like marketing than research. It conveniently excludes key players like Gemini and OpenAI, right as Apple is reportedly working on partnerships with them.

It's hard to believe this paper is a serious research effort into the limits of LRM. It looks more like a way to **justify why Apple is behind in the AI race**.

And if this _is_ the level of research Apple is putting out, they're already out of the game.

So, Mr. Cook (loyal reader of my blog, I'm sure):  
Forget GPT. **Throw out the perceptron. Build something new.** [The perceptron is outdated](https://dariotortorici.github.io/blog/perceptron-is-dead/).

---
Image Credits: Apple's Paper
