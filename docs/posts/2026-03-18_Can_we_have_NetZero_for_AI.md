---
date: 2026-03-18
categories:
  - Thought
tags:
  - Thought
  - Carbon Neutrality
  - AI
  - Spiking
  - Neuromorphic
hide:
  - toc
authors:
  - khanh
---



# Carbon-Neutral AI: Rethinking How Intelligence Uses Energy

Artificial Intelligence is advancing at an incredible pace. From large-scale models to autonomous systems, modern AI continues to push the limits of computation. However, this progress raises an important question:

**How sustainable is AI?**

Training and running modern AI systems can consume enormous amounts of energy. Recent studies estimate that training large AI models can require **hundreds of MWh of electricity**, while data centers already account for roughly **1–2% of global electricity consumption**[^1]. As AI continues to scale, its carbon footprint will inevitably grow unless we rethink how these systems operate. As shown below, we can see that AI energy consumption may soon exceed the consumption of a country with 100 million people.

![AI power demand](imgs/2026-03-18_AI_power_demand.png#only-light){ width="100%" }
![AI power dman](imgs/2026-03-18_AI_power_demand-inv.png#only-dark){ width="100%" }
*Figure 1: AI power demand project vs energy consumption of Japan in 2024.*

Most research today focuses on making AI **more computationally efficient** through pruning, quantization, or model compression. While effective, these approaches still assume that energy is always available.

But what if AI systems could **adapt their computation to the energy available**?

<!-- more -->

## Intelligence That Adapts to Energy

In nature, biological systems operate under strict energy constraints. The human brain, for example, consumes only about **20 watts**, yet it performs tasks that still challenge modern AI systems.

Inspired by this principle, we explore how AI can operate under similar energy constraints.

Our work introduces **GreenMorph**[^3], a framework designed for sustainable neuromorphic computing. The core idea is simple:

> **AI systems should scale their computation based on the energy available to them.**

Instead of assuming a stable power supply, GreenMorph targets environments powered by energy harvesting, such as solar or ambient sources. In these scenarios, energy availability can fluctuate significantly over time, meaning the AI system must dynamically adapt its workload. As we know, when humans are hungry (lack of energy), we can still think and react, but at a reduced cognitive level[^2]. Inspired by this behavior, we aim to adapt this principle from nature into our system design.

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

Future AI systems, especially those deployed in edge devices, drones, robots, and autonomous platforms, may increasingly rely on renewable or harvested energy sources. In such environments, AI systems should not assume unlimited power. Instead, they should **adapt their computation to match the energy they receive**.

If AI systems can dynamically adjust their workload to energy availability, it becomes possible to approach **carbon-neutral or net-zero AI computation**.

### Training Energy Adaptation to Various Energy Conditions

This table provides a sneak peek into our proposed GreenMorph, demonstrating how training dynamically adapts to varying energy conditions. By adjusting parameters such as timestep and neuron count, the system maintains energy-aware operation while preserving high accuracy. Please refer to the full paper for more details.


*Single node (Raspberry Pi 5; network configuration: 784–700 with lateral inhibitory winner-take-all mechanism; on-chip STDP learning)*

| Weather | Battery   | Harvest (Wh) | Consumption (Wh) | Energy Deficit (%) | Adjusted Variables              | Adapted Consumption (Wh) | Accuracy |
|--------|-----------|-------------|------------------|--------------------|--------------------------------|---------------------------|----------|
| sunny  | fresh     | 174.24      | 172.50           | 0.00               | None                           | 174.24                    | 0.9057   |
| sunny  | mid       | 160.30      | 172.50           | 7.07               | T_timestep                     | 156.10                    | 0.9051   |
| sunny  | wear-out  | 146.36      | 172.50           | 15.15              | T_timestep                     | 140.00                    | 0.9093   |
| cloudy | fresh     | 159.12      | 172.50           | 7.76               | T_timestep                     | 158.90                    | 0.9050   |
| cloudy | mid       | 159.12      | 172.50           | 7.76               | T_timestep                     | 158.90                    | 0.9050   |
| cloudy | wear-out  | 146.36      | 172.50           | 15.15              | T_timestep                     | 140.00                    | 0.9093   |
| rainny | fresh     | 20.52       | 172.50           | 88.10              | T_timestep, N_neurons          | 19.95                     | 0.8756   |
| rainny | mid       | 20.52       | 172.50           | 88.10              | T_timestep, N_neurons          | 19.95                     | 0.8756   |
| rainny | wear-out  | 20.52       | 172.50           | 88.10              | T_timestep, N_neurons          | 19.95                     | 0.8756   |

## Looking Forward

This work will be presented at the  

> Hanyu Yuga, Subbaiah Ravi Hariprakash, Abderazek Ben Abdallah, Zhishang Wang, and Khanh N. Dang  
> *GreenMorph: Sustainable Neuromorphic Computing through Energy Harvesting and Energy Driven Online STDP Learning*  
> IEEE International Symposium on Circuits and Systems (ISCAS), 2026.


As AI continues to expand across embedded systems and intelligent machines, sustainability will become a fundamental design requirement.

The future of AI may not simply be **bigger models**.

It may be **intelligence that understands its energy footprint and adapts accordingly**.


[^1]:   Data centres will use twice as much energy by 2030 — driven by AI. URL: [https://www.nature.com/articles/d41586-025-01113-z](https://www.nature.com/articles/d41586-025-01113-z)
[^2]: Hunger and Performance in the Classroom. URL: [https://www.econstor.eu/handle/10419/207452](https://www.econstor.eu/handle/10419/207452)
[^3]: Hanyu Yuga, Subbaiah Ravi Hariprakash, Abderazek Ben Abdallah, Zhishang Wang, and Khanh N. Dang , "*GreenMorph: Sustainable Neuromorphic Computing through Energy Harvesting and Energy Driven Online STDP Learning*", IEEE International Symposium on Circuits and Systems (ISCAS), 2026.