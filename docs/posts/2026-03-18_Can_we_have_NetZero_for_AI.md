---
date: 2026-03-18
categories:
  - Thought
tags:
  - Journey
hide:
  - toc
authors:
  - khanh
---



# Carbon-Neutral AI: Rethinking How Intelligence Uses Energy

Artificial Intelligence is advancing at an incredible pace. From large-scale models to autonomous systems, modern AI continues to push the limits of computation. However, this progress raises an important question:

**How sustainable is AI?**

Training and running modern AI systems can consume enormous amounts of energy. Recent studies estimate that training large AI models can require **hundreds of MWh of electricity**, while data centers already account for roughly **1–2% of global electricity consumption**. As AI continues to scale, its carbon footprint will inevitably grow unless we rethink how these systems operate.

Most research today focuses on making AI **more computationally efficient** through pruning, quantization, or model compression. While effective, these approaches still assume that energy is always available.

But what if AI systems could **adapt their computation to the energy available**?

<!-- more -->

## Intelligence That Adapts to Energy

In nature, biological systems operate under strict energy constraints. The human brain, for example, consumes only about **20 watts**, yet it performs tasks that still challenge modern AI systems.

Inspired by this principle, we explore how AI can operate under similar energy constraints.

Our work introduces **GreenMorph**, a framework designed for sustainable neuromorphic computing. The core idea is simple:

> **AI systems should scale their computation based on the energy available to them.**

Instead of assuming a stable power supply, GreenMorph targets environments powered by **energy harvesting**, such as solar or ambient sources. In these scenarios, energy availability can fluctuate significantly over time, meaning the AI system must dynamically adapt its workload.


## Why Spiking Neural Networks?

GreenMorph is built using **Spiking Neural Networks (SNNs)**, a class of neural networks inspired by biological neurons.

Unlike conventional neural networks that process information continuously, SNNs operate in an **event-driven manner**. Computation only occurs when spikes are generated, allowing systems to remain mostly idle when there is no activity.

This event-driven behavior can significantly reduce power consumption. Neuromorphic hardware implementations have demonstrated **orders-of-magnitude improvements in energy efficiency** compared to conventional deep learning accelerators.


## Energy-Driven Learning and Computation

To further improve efficiency, GreenMorph introduces mechanisms that dynamically adapt the computational workload:

1. **Timestep reduction during training**, which reduces unnecessary simulation steps in SNN learning  
2. **Neuron similarity-based pruning**, which removes redundant neural activity during inference  
3. **Energy-driven learning**, where the system adapts its behavior according to the available energy budget  

Together, these techniques allow the system to **trade computation for energy savings** when necessary.

In our experiments, this approach can reduce **training energy consumption by up to 88%**, while maintaining competitive model accuracy. Inference energy can also be scaled depending on the available energy budget and desired operating mode.


## Toward Net-Zero AI

The broader vision of this work is **carbon-aware AI computation**.

Future AI systems—especially those deployed in edge devices, drones, robots, and autonomous platforms—may increasingly rely on renewable or harvested energy sources. In such environments, AI systems should not assume unlimited power. Instead, they should **adapt their computation to match the energy they receive**.

If AI systems can dynamically adjust their workload to energy availability, it becomes possible to approach **carbon-neutral or net-zero AI computation**.


## Looking Forward

This work will be presented at the  
:contentReference[oaicite:0]{index=0}.

> Hanyu Yuga, Subbaiah Ravi Hariprakash, Abderazek Ben Abdallah, Zhishang Wang, and Khanh N. Dang  
> *GreenMorph: Sustainable Neuromorphic Computing through Energy-Harvesting and Energy-Driven Online STDP Learning*  
> IEEE International Symposium on Circuits and Systems (ISCAS), 2026.

As AI continues to expand across embedded systems and intelligent machines, sustainability will become a fundamental design requirement.

The future of AI may not simply be **bigger models**.

It may be **intelligence that understands its energy footprint—and adapts accordingly**.

!!! note "Disclaimer"
    This article is edited by ChatGPT.
