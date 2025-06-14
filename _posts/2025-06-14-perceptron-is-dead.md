---
layout: post
title: "The Perceptron is dead"
excerpt: "The same neuron can use different learning rules that perceptron fails to model.<br/>"
image: /assets/images/blog_thumbnails/perceptron_dead.png
date: 2025-06-11
categories: 
  - Personal growth
tags:
  - learning
  - digital-detox
---

# TLDR
The same neuron can use different learning rules that perceptron fails to model.

---

# Article

I recently watched an [extremely interesting video](https://www.youtube.com/watch?v=9StHNcGs-JM) that presents a study published in _Science_. The core finding is simple but disruptive: **the same neuron can use different learning rules depending on the distance of the synapse from the soma (the cell body)**. The research focused on pyramidal neurons in the motor cortex. Synapses near the soma, in the basal dendrites, follow Hebbian learning, the classic “neurons that fire together wire together.” But synapses farther away, in the apical dendrites, strengthen **without** the neuron firing, based instead on local co-activation with nearby synapses.

This forces us to reconsider a foundational assumption in computational neuroscience. **Our models are too simple.**

We built artificial neural networks on the concept of the perceptron: weighted inputs, a threshold, an output. It is a powerful abstraction (from when we realised we had to use many with backpropagation), but perhaps too simplistic.

A real neuron is not a single uniform function. It's a **compartmentalised, hierarchical system**, with complex, nonlinear interactions taking place locally, inside dendrites. These aren't just passive cables for input signals. They **compute**. A single biological neuron is already, functionally, a small network.

This leads to an uncomfortable but necessary question: _How much are we limiting ourselves by forcing all learning to follow the same rule everywhere in the network?_
Maybe the real step forward isn't about bigger models. Maybe it's about **richer units**

---

Image Credits: Artem Kirsanov
