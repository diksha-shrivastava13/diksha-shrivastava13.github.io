---
title: "Beyond Correctness: Generating New Problems from Divergent Solutions for Reasoning with Rearrangement Sampling" 
date: 2025-01-10
lastmod: 2025-03-09
tags: ["Reinforcement Learning","Rejection Sampling","Reward Modeling","Post-Training"]
author: ["Diksha Shrivastava", "Mann Acharya", "Dr. Tapas Badal"]
description: "" 
summary: "Rearrangement Sampling transforms rejected solutions into new problem statements, expanding the problem-solution space beyond correctness constraints. A larger model acts as a judge to assess whether alternative problems can be inferred from divergent completions, assigning structured rewards to prior generations. This enables efficient data reuse, improves distributional coverage, and enhances reasoning generalization across domains." 
cover:
    image: "paper1.png"
    relative: false
editPost:
    URL: https://github.com/Entangled-Causality
    Text: "Work in Progress"
---

##### Preliminary Abstract

Traditional training paradigms in mathematical reasoning, code generation, and natural language tasks enforce correctness via explicit reward signals, overlooking the latent structure within incorrect yet coherent outputs. We introduce Rearrangement Sampling, a framework that repurposes rejected solutions by reconstructing corresponding problem statements, enabling models to generalize beyond correctness. Given an initial task producing 
𝑛 divergent completions, a larger model acts as a judge—akin to RLAIF—to determine whether each completion can be mapped to a valid alternative problem. This process expands the problem-solution space by generating 
𝑛 − 1 additional problems per task, each inheriting solutions from the original distribution with assigned relative rewards. By leveraging incorrect yet interpretable generations, Rearrangement Sampling increases the efficiency of data reuse, enhances distributional coverage, and enables more structured exploration of reasoning pathways in learning systems.
