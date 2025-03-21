---
title: "Agents are Decision-Makers First: Leveraging Graph of Decisions for Intermediate Reward Modeling" 
date: 2025-02-09
lastmod: 2025-01-10
tags: ["Reinforcement Learning","Decision-Making","Reward Modeling","Post-Training", "Agents"]
author: ["Diksha Shrivastava", "Mann Acharya", "Dr. Tapas Badal"]
description: "" 
summary: "GoD-IRM introduces intermediate reward modeling for structured decision-making in language models, assigning rewards at each divergence point in a reasoning trajectory. This approach enables fine-grained credit assignment, improving model robustness in long-horizon problem-solving. By reinforcing decision-making rather than just final outputs, GoD-IRM aligns language models more closely with traditional agent-based RL." 
cover:
    image: "paper1.png"
    relative: false
editPost:
    URL: https://github.com/diksha-shrivastava13
    Text: "Work in Progress"
---

##### Preliminary Abstract

Traditional reinforcement learning (RL) defines agents as decision-makers that interact with their environment, observe 
state changes, and update future actions based on received rewards. In language model reasoning, however, training 
methods primarily reinforce final outputs, neglecting the intermediate decision-making process that guides solution 
trajectories. We propose Graph of Decisions for Intermediate Reward Modeling (GoD-IRM), a structured framework that 
assigns reward signals at every branching decision in a reasoning trajectory. Unlike existing rejection sampling and 
GRPO methods, which reinforce only correct completions, our approach models decision divergence, attributing higher 
rewards to paths that remain aligned with the optimal solution longer while penalizing early deviations. By 
structuring the solution space as a graph of decision nodes, GoD-IRM captures critical decision points, enabling 
models to learn more fine-grained decision-making heuristics and improving robustness in long-horizon reasoning tasks.
