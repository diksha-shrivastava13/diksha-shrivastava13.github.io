---
title: "Closing the Loop: Execution-Guided Continuous Generation for Adaptive Model Reasoning" 
date: 2025-01-08
lastmod: 2025-03-08
tags: ["Language Model Reasoning", "Post-Training", "Reward Modeling", "Decision-Making", "Rejection Sampling", "Reinforcement Learning"]
author: ["Diksha Shrivastava", "Mann Acharya", "Dr. Tapas Badal"]
description: "" 
summary: "We propose a feedback-driven decoding method where each generated candidate is iteratively refined using execution traces or reward-based adjustments. By conditioning generation on structured feedback from previous attempts, the method enforces progressive error minimization and adaptive correction. This approach enhances model reasoning, reduces compounding failure modes, and improves convergence in both code generation and reinforcement learning-based post-training." 
cover:
    image: "paper1.png"
    relative: false
editPost:
    URL: https://github.com/diksha-shrivastava13
    Text: "Work in Progress"
---

##### Preliminary Abstract

Standard autoregressive decoding in large language models (LLMs) generates multiple completions per query but lacks 
mechanisms for iterative self-improvement. We propose a method that integrates environment feedback into the generation 
process, ensuring that each subsequent candidate 𝑛 + 1 is conditioned on the feedback received by candidate 
𝑛, producing a progressively informed sequence of outputs. In code generation, this involves executing generated 
programs, analyzing runtime traces, and refining subsequent completions to systematically reduce errors. 
In reinforcement learning-based post-training, the method replaces static ranking with verifiable reward-driven 
refinement, allowing models to iteratively adjust based on structured feedback rather than predefined preferences.
By explicitly modeling iterative self-correction, this approach enables progressive error minimization, improves 
adaptive reasoning, and enhances task-specific generalization. Empirical results will evaluate its impact on code 
synthesis and decision-making tasks, demonstrating improvements in functional correctness and reward optimization.
