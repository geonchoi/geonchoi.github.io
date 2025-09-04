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

Polar codes, discovered by Arıkan in 2009, are the first provably capacity-achieving codes with explicit construction. However, their finite-length performance and decoding complexity present challenges for practical implementation, especially in ultra-reliable low-latency communication (URLLC) scenarios.

#### Error Analysis and Mitigation Strategies

SCL decoding of polar codes faces two fundamental error types that significantly impact performance in short packet scenarios. Understanding these error mechanisms is crucial for developing targeted solutions:

**→ [Detailed Error Analysis: Error Probability in SCL Decoding](/research/error-probability-analysis/)**  
*Comprehensive analysis of Type I (path elimination) and Type II (incorrect selection) errors with theoretical bounds and mitigation strategies*

**Targeted Solutions for Specific Error Types**:
- **Deep Polar Codes**: Address Type II errors through multi-layer concatenation
- **SPP Codes**: Focus on Type I error reduction via strategic pre-transformation

#### Flexible Blocklength Support

Polar codes are naturally constructed for blocklengths $N = 2^n$, but practical systems require arbitrary lengths. This fundamental constraint necessitates sophisticated rate-matching techniques that can adapt polar codes to real-world requirements while preserving performance.

**→ [Technical Details: Rate-Matching Techniques](/research/rate-matching-techniques/)**  
*Advanced shortening, puncturing, and repetition strategies with performance analysis and implementation guidelines*

![Polar Code Construction](../assets/images/research/polar_construction.png)
*Figure 1: Polar code construction and channel polarization phenomenon*

#### Deep Polar Codes for Type II Error Mitigation

Deep polar codes address **incorrect codeword selection errors** (Type II errors) through innovative multi-layer concatenated structures that improve weight distribution and minimum distance properties.

![Deep Polar Structure](../assets/images/research/deep_polar_structure.png)
*Figure 2: Multi-layer serially concatenated structure targeting Type II error reduction*

**Key Innovations**:
- **Weight distribution optimization**: Multi-layer concatenation for enhanced minimum distance
- **Type II error mitigation**: Specifically addresses incorrect path selection at final decision stage
- **URLLC reliability**: Targets ultra-high reliability requirements (10^-9 error rates)

**→ [Read More: Deep Polar Codes Research](/research/deep-polar-codes/)**  
*Comprehensive analysis of multi-layer architecture, mathematical framework, and performance validation*

#### Sparsely Pre-transformed Polar (SPP) Codes for Type I Error Reduction

SPP codes specifically target **correct codeword elimination errors** (Type I errors) through strategic pre-transformation that preserves correct paths during SCL decoding:

![SPP Pre-transformation](../assets/images/research/spp_pretransform.png)
*Figure 3: Sparse pre-transformation preventing correct path elimination*

**Core Mechanism**:
- **Path preservation strategy**: Prevents correct paths from being eliminated prematurely
- **Type I error mitigation**: Addresses early decision errors in SCL decoding tree
- **Strategic bit positioning**: Consecutive information bits are separated to reduce error propagation

**Technical Advantages**:
- Maintains SCL decoding complexity while improving path retention
- Compatible with existing decoder architectures
- Significant performance gains with minimal implementation overhead

#### Rate-Matching for Flexible Blocklength Support

The fundamental $N = 2^n$ constraint of polar codes creates significant challenges for practical deployment, where arbitrary packet sizes and system requirements demand flexible blocklength support:

![Rate Matching Overview](../assets/images/research/rate_matching_schemes.png)
*Figure 4: Rate-matching enabling flexible polar code deployment in real systems*

**Essential Techniques**:
- **Advanced Shortening**: Bit-reversal and reliability-based approaches
- **Intelligent Puncturing**: QUP and distributed puncturing strategies  
- **Strategic Repetition**: Systematic and coded repetition schemes
- **Hybrid Methods**: Multi-kernel and nested polar constructions

**→ [Technical Implementation: Rate-Matching Techniques](/research/rate-matching-techniques/)**  
*Comprehensive guide including advanced algorithms, performance analysis, and hardware considerations*

### Deep Learning-Enhanced Error Correction

#### Neural Network-Based Decoders

Modern communication systems benefit from machine learning approaches to channel coding:

![Neural Decoder Architecture](../assets/images/research/neural_decoder_arch.png)
*Figure 5: Deep neural network decoder architecture for error correction*

**Error Correction Convolutional Transformer (ECCT)**:
- **High-order modulation adaptation**: Optimized training for complex constellation schemes
- **Non-binary code support**: Extended ECCT design for q-ary codes
- **Performance-complexity trade-offs**: Efficient implementation strategies

**Research Directions**:
- Joint source-channel coding with neural networks
- Adaptive decoding based on channel conditions
- Hardware-friendly neural decoder architectures

### Non-Coherent Communication Systems

Short packet transmission scenarios face significant pilot overhead challenges. Non-coherent transmission eliminates the need for explicit channel estimation:

![Non-coherent System Model](../assets/images/research/noncoherent_system.png)
*Figure 6: Non-coherent polar-coded communication system over block-fading channels*

#### Code-Splitting Techniques

**System Model**:
- Block-fading channels without channel state information (CSI)
- Polar code construction adapted for non-coherent scenarios
- Joint detection and decoding strategies

**Technical Contributions**:
- Information-theoretic analysis of non-coherent polar codes
- Practical decoder implementations with reasonable complexity
- Performance analysis under various fading conditions

### Semantic Communication and Unequal Error Protection

Modern communication systems require awareness of semantic importance in transmitted data:

![Semantic Communication Framework](../assets/images/research/semantic_framework.png)
*Figure 7: Semantic communication system with importance-aware channel coding*

**Key Innovations**:
- **Message importance mapping**: Different protection levels based on semantic significance
- **Adaptive coding schemes**: Dynamic adjustment based on content importance
- **Task-oriented optimization**: End-to-end optimization for specific applications

### State Estimation and Signal Processing

#### Split-KalmanNet for Robust Estimation

Traditional Kalman filtering faces challenges in non-linear and uncertain environments:

![Split-KalmanNet Architecture](../assets/images/research/split_kalmannet.png)
*Figure 8: Split-KalmanNet architecture for robust state estimation*

**Technical Approach**:
- **Neural network enhancement**: ML-assisted Kalman filter updates
- **Split architecture**: Separate processing for prediction and correction
- **Vehicular applications**: Robust tracking in dynamic environments

### Integrated Radar and Communication Systems

#### Joint Radar-Communication Design

Modern systems require spectrum-efficient solutions that serve both radar and communication functions:

![Joint Radar-Comm System](../assets/images/research/joint_radar_comm.png)
*Figure 9: Integrated radar and communication system architecture*

**Research Focus**:
- **Information-theoretic foundations**: Fundamental limits of joint systems
- **Pulse-Doppler integration**: Waveform design for dual functionality
- **Spectrum sharing strategies**: Efficient coexistence mechanisms

## Ongoing Projects

### Project 1: Advanced Polar Code Constructions
**Duration**: 2024 - Present  
**Funding**: National Research Foundation of Korea

Developing next-generation polar codes for 6G applications with focus on:
- Ultra-low latency requirements (< 1ms)
- High reliability targets (10^-9 error rates)
- Energy-efficient implementations

### Project 2: ML-Enhanced Channel Coding
**Duration**: 2024 - Present  
**Collaboration**: Industry Partner

Investigating neural network approaches for:
- Adaptive decoding algorithms
- Joint optimization with physical layer
- Hardware acceleration strategies

### Project 3: Semantic Communication Systems
**Duration**: 2024 - Present  
**Focus**: Task-oriented communication

Developing coding schemes that consider:
- Message semantic importance
- End-to-end system optimization
- Real-time adaptation capabilities

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

## Future Research Directions

### Near-term Goals (2024-2025)
- Complete development of SPP codes for 5G-Advanced
- Publish comprehensive study on deep polar codes
- Establish collaboration framework for semantic communication

### Long-term Vision (2025-2027)
- Develop unified framework for ML-enhanced channel coding
- Pioneer semantic-aware communication systems
- Contribute to 6G standardization efforts

---

## Collaboration Opportunities

I am actively seeking collaborations in:
- **Industry Partnerships**: Practical implementation of research outcomes
- **Academic Collaborations**: Joint research projects and student exchanges
- **Standardization Efforts**: Contributing to next-generation communication standards

**Contact**: [geon.choi@postech.ac.kr](mailto:geon.choi@postech.ac.kr)

---

*For a complete list of publications and technical details, please visit the [Publications](/publications/) page.*