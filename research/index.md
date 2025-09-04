---
layout: page
title: "Research"
crawlertitle: "Research"
permalink: /research/
active: Research
---

# Research

My research interests span information theory, channel coding, and machine learning applications in wireless communications. I focus on developing novel coding schemes and optimization techniques for next-generation wireless systems, with particular emphasis on short packet communications and URLLC scenarios.

## Current Research Areas

### Polar Codes and Advanced Coding Techniques

#### Polar Code Overview

Polar codes, discovered by Arıkan in 2009, are the first provably capacity-achieving codes with explicit construction. They exploit the channel polarization phenomenon to achieve capacity with low encoding/decoding complexity of O(N log N). However, finite-length performance and specific error patterns in successive cancellation list (SCL) decoding present challenges for URLLC applications.

![Polar Code Construction](../assets/images/research/polar_construction.png)
*Figure 1: Polar code construction and channel polarization phenomenon*

Polar codes face two fundamental challenges in practical deployment: **decoding errors** (Type I: path elimination, Type II: incorrect selection) and **blocklength constraints** (natural construction for N = 2^n only). My research develops targeted solutions addressing these specific limitations.

**→ [Detailed Research: Polar Codes and Advanced Techniques](/research/polar-codes/)**  
*Comprehensive coverage including deep polar codes, SPP codes, rate-matching techniques, and non-coherent transmission*


### Deep Learning-Enhanced Error Correction

Modern communication systems increasingly benefit from machine learning approaches to channel coding. My research focuses on neural network-based decoders that can learn optimal decision boundaries and adapt to channel conditions, particularly for non-binary codes and high-order modulation schemes.

![Neural Decoder Architecture](../assets/images/research/neural_decoder_arch.png)
*Figure 2: Deep neural network decoder architecture for error correction*

Key innovations include Error Correction Convolutional Transformer (ECCT) optimized for high-order modulation, non-binary code extensions, and hardware-friendly implementations that balance performance with computational complexity.

**→ [Detailed Research: Deep Learning-Enhanced Error Correction](/research/ml-enhanced-coding/)**  
*Neural decoder architectures, training methodologies, and performance-complexity trade-offs*


### Signal Processing and State Estimation

Robust state estimation is crucial for dynamic wireless environments, particularly in vehicular communications and IoT scenarios. My research develops ML-enhanced filtering techniques that outperform traditional approaches under non-linear and uncertain conditions.

![Split-KalmanNet Architecture](../assets/images/research/split_kalmannet.png)
*Figure 3: Split-KalmanNet architecture for robust state estimation*

The Split-KalmanNet approach separates prediction and correction phases, enabling neural network enhancement while preserving the theoretical foundations of Kalman filtering.

**→ [Detailed Research: Signal Processing and State Estimation](/research/signal-processing/)**  
*Split-KalmanNet design, vehicular applications, and performance analysis*

### Integrated Radar and Communication Systems

Spectrum-efficient solutions that serve both radar sensing and communication functions are essential for future wireless systems. My research establishes information-theoretic foundations for joint system design and develops practical waveform optimization techniques.

![Joint Radar-Comm System](../assets/images/research/joint_radar_comm.png)
*Figure 4: Integrated radar and communication system architecture*

Focus areas include fundamental limits analysis, pulse-Doppler integration strategies, and spectrum sharing mechanisms that enable coexistence without performance degradation.

**→ [Detailed Research: Integrated Radar and Communication](/research/radar-communication/)**  
*Information-theoretic foundations, waveform design, and spectrum sharing strategies*


### Semantic Communication and Unequal Error Protection

Modern communication systems require awareness of semantic importance in transmitted data. Different parts of a message vector carry varying significance depending on the application task, necessitating adaptive protection schemes.

![Semantic Communication Framework](../assets/images/research/semantic_framework.png)
*Figure 5: Semantic communication system with importance-aware channel coding*

My research develops coding schemes that dynamically adjust protection levels based on semantic importance, enabling task-oriented optimization and improved end-to-end performance.

**→ [Detailed Research: Semantic Communication](/research/semantic-communication/)**  
*Importance-aware coding, adaptive protection schemes, and task-oriented optimization*

## Ongoing Projects

### Project 1: Advanced Polar Code Constructions
**Duration**: 2024 - Present  
**Funding**: National Research Foundation of Korea

Developing next-generation polar codes for 6G applications with focus on ultra-low latency requirements (< 1ms), high reliability targets (10^-9 error rates), and energy-efficient implementations.

### Project 2: ML-Enhanced Channel Coding
**Duration**: 2024 - Present  
**Collaboration**: Industry Partner

Investigating neural network approaches for adaptive decoding algorithms, joint optimization with physical layer, and hardware acceleration strategies.

### Project 3: Semantic Communication Systems
**Duration**: 2024 - Present  
**Focus**: Task-oriented communication

Developing coding schemes that consider message semantic importance, end-to-end system optimization, and real-time adaptation capabilities.


## Research Philosophy

My research philosophy centers on bridging theoretical rigor with practical impact:

**Core Principles**:
- **Theory-Practice Bridge**: Developing theoretically sound solutions with clear practical benefits
- **Interdisciplinary Approach**: Leveraging machine learning to enhance classical communication techniques
- **Implementation Focus**: Creating efficient algorithms suitable for real-world deployment
- **Collaborative Research**: Fostering partnerships between academia and industry

**Methodological Approach**:
1. **Problem Identification**: Focus on genuine challenges in modern communication systems
2. **Theoretical Foundation**: Establish solid mathematical framework for proposed solutions
3. **Algorithm Development**: Create efficient and implementable solutions
4. **Performance Validation**: Comprehensive evaluation under realistic conditions
5. **Practical Implementation**: Consider hardware constraints and real-world deployment

## Collaboration Opportunities

I am actively seeking collaborations in:
- **Industry Partnerships**: Practical implementation of research outcomes
- **Academic Collaborations**: Joint research projects and student exchanges
- **Standardization Efforts**: Contributing to next-generation communication standards

**Contact**: [geon.choi@postech.ac.kr](mailto:geon.choi@postech.ac.kr)

---

*For a complete list of publications and technical details, please visit the [Publications](/publications/) page.*
