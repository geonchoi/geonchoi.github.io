---
layout: page
title: "Polar Codes and Advanced Coding Techniques"
crawlertitle: "Polar Codes Research"
permalink: /research/polar-codes/
---

# Work in progress

# Polar Codes and Advanced Coding Techniques

[← Back to Research](/research/)

## Overview

Polar codes represent a fundamental breakthrough in channel coding theory, being the first provably capacity-achieving codes with explicit construction. My research addresses the practical challenges of polar codes in next-generation wireless systems, developing advanced techniques for URLLC, short packet transmission, and flexible deployment scenarios.


### Channel Polarization Phenomenon

Polar codes exploit the remarkable channel polarization phenomenon discovered by Arıkan in 2009. Through recursive channel combining and splitting operations, a set of N synthetic channels becomes either nearly perfect or nearly useless:

$$W_N^{(i)}: \mathcal{X} \to \mathcal{Y}^N \times \mathcal{X}^{i-1}$$

<img src="/assets/images/research/polarcode/polarization.png" width="90%" alt="Polar Code Construction">
*Figure 1: Polar code construction and channel polarization phenomenon.*


### Successive Cancellation (SC) Decoding

The basic SC decoder processes bits sequentially, making hard decisions at each step:

$$\hat{u}_i = \begin{cases}
0 & \text{if } i \in \mathcal{F} \\
\arg\max_{u_i} W_N^{(i)}(y_1^N, \hat{u}_1^{i-1} | u_i) & \text{if } i \in \mathcal{I}
\end{cases}$$
where $\mathcal{F}$ is the frozen set and $\mathcal{I}$ is the information set.

<img src="/assets/images/research/polarcode/sc_decoding.png" width="90%" alt="SC decoding">
*Figure 2: Successive cancellation decoding.*

The SC list (SCL) decoder maintains upto $L$ decoding paths to improve the decoding performance.


**Key Properties**:
- **Capacity Achievement**: Polar codes achieve the symmetric capacity I(W) of the underlying channel
- **Explicit Construction**: No random codes needed - completely deterministic construction
- **Low Complexity**: Encoding and decoding complexity of O(N log N)
<!-- - **Recursive Structure**: Natural binary tree structure enabling efficient processing -->


## Practical Challenges and Solutions

Polar codes face two fundamental challenges in practical deployment: finite-blocklength performance and blocklength constraints (natural construction for $N = 2^n$ only). My research develops targeted solutions addressing these specific limitations.


### Challenge 1: Finite-Length Performance

While polar codes are asymptotically capacity-achieving, their finite-length performance, especially for short packets, requires enhancement through advanced techniques.

Understanding and addressing specific error mechanisms in SCL decoding is crucial for optimal performance.

**Type I Error $(\epsilon_1)$ - Path Elimination**:
- Correct path eliminated from decoding candidate list
- Dominates at low SNR and small list size
- Addressed by SPP codes

**Type II Error $(\epsilon_2)$ - Incorrect Selection**:
- Wrong path selected from remaining candidates
- Dominates at high SNR and large list size due to minimum distance
- Addressed by deep polar codes

<img src="/assets/images/research/polarcode/scl_error_event.png" width="90%" alt="SCL error event table">
*Figure 3: Two types of error event of SCL decoder.*



#### Deep Polar Codes: Multi-Layer Concatenation

**Problem Addressed**: Type II errors (incorrect codeword selection) in SCL decoding by reducing the number of low-weight codewords.


**Technical Innovation**:
- **Serially Concatenated Structure**: Multiple polar kernel matrices as pre-transformation layers
- **Weight Distribution Enhancement**: Improved minimum distance properties


<img src="/assets/images/research/polarcode/deep_polar_layer.png" width="90%" alt="deep polar multi-layer improvement example">
*Figure 4: Deep polar codes multi-layer architecture addressing Type II errors.*

As shown in Figure 4, incresing the number of pre-transform layer can improve the weight spectrum of the corresponding code.

<img src="/assets/images/research/polarcode/deep_polar_bec.png" width="80%" alt="BLER at BEC deep polar">
*Figure 5: Decoding performance comparison across different techniques and scenarios.*

Figure 5 present simulation result at binary erasure channel (BEC) with various code parameters, i.e., the size of message bits and codeword bits. Across the various code parameters, our pre-transform structure effectively improve the weight spectrum, as shown the enhanced decoding performance under ML decoding, which can be obtained by SCL decoder with moderate and large list sizes. 

#### Sparsely Pre-transformed Polar (SPP) Codes

**Problem Addressed**: Type I errors (correct codeword elimination) in SCL decoding by limiting the number of consecutive (semi-polarized) information bits.

We introduce two types of pre-transform, each of which aims to reduce $P(\epsilon_1)$ and $P(\epsilon_2)$. The overall encoding structure is illustrated in Figure 6.

<img src="/assets/images/research/polarcode/spp_code.png" width="90%" alt="SPP encoding structure">
*Figure 6: SPP codes preventing correct path elimination through pre-transformation.*

**Two types of pre-transform**:
- **Type-I pre-transform**: prevents the use of consecutive semi-polarized information bits. To show the impact of consecutive semi-polarized information bits, we present figure 7, in which the error probability of $\epsilon_1$, i.e., $P(\epsilon_1)$ is decreased by limiting the use of consecutive information bits.
<img src="/assets/images/research/polarcode/spp_consecutive_impact.png" width="65%" alt="effect of non-consecutive info bits">
*Figure 7: The effect of consecutive semi-polarized information bits.*

- **Type-II pre-transform**: targets to reduce the number of low-weight codewords.

Figure 8 present simulation result at AWGN channel with various code parameters. Our solutions (Deep polar codes and SPP codes) shows superior error-correcting performance compared to 5G CA polar codes. 

<img src="/assets/images/research/polarcode/spp_bler.png" width="100%" alt="SPP BLER performance">
*Figure 8: Decoding performance comparison across different techniques and scenarios.*

### Challenge 2: Blocklength Flexibility
Polar codes naturally support blocklengths $N = 2^n$ only.
In 5G NR, the following methods are available for supporting arbitrary blocklengths.

The inherent constraint of Arıkan's construction limits polar code lengths to powers of two, i.e., $M = 2^n$. To support arbitrary codeword lengths $M \neq 2^n$, rate-matching techniques are employed:
- **Shortening and Puncturing:** Used to reduce code length from a larger mother code of size $N > M$. 
- **Extension and Repetition:** Used to increase code length from a smaller mother code of size $N < M$.

In 5G NR systems, quasi-uniform puncturing, shortening, and repetition with sub-block interleaving are employed for rate-matching, ensuring compatibility while maintaining good performance. Shortening removes the last $N-M$ interleaved codeword bits, while puncturing removes the first $N-M$ bits. Repetition extends the first $M-N$ interleaved codeword bits.

#### Motivation
While shortening and puncturing is excellent rate-matching techniques in practive, they requires the decoding of mother code, whose size is at most double compared to required codeword sizes. So, 5G NR adopts repetition based methods for low rate code. However, repetition gives limited coding gain compared to other methods. 

Sometimes, extension-based methods can offer superior performance with reduced complexity when the desired code length exceeds a power of two.

#### Our Solution
We introduce a systematic extension method that leverages the hierarchical encoding structure of deep polar codes by concatenating partial codewords from different transformation layers. 
The encoding process generates multiple codewords from each layer, which are then concatenated to form a longer code, enabling flexible blocklengths that are not limited to powers of two (Figure 9).
<img src="/assets/images/research//polarcode/deep_polar_extension.png" width="90%" alt="Extension encoder">
*Figure 9: The encoding for single-layer extended deep polar codes.*

The resultant codeword exhibit the improved channel polarization as shown in figure 10.
<img src="/assets/images/research//polarcode/improved_polarization.png" width="90%" alt="Improved polarization">
*Figure 10: Improved channel polarization by our method.*

We design an efficient LLR-combined successive cancellation list (SCL) decoding algorithm that incorporates soft information from pre-transform layers into the primary decoding process (Figure 11). The decoder first applies soft-output SCL decoding to the extended segments to estimate soft information, then uses a modifed SCL decoder that combines both the original LLR values and the soft information from connection bits. 

<img src="/assets/images/research//polarcode/extension_code_decoding.png" width="60%" alt="Extension decoder">
*Figure 11: The decoding for single-layer extended deep polar codes.*

Figure 12 shows the effectivenes of our extension scheme compareed to repetition for rate-matching.
<img src="/assets/images/research/polarcode/extension_bler.png" width="80%" alt="Extension code BLER">
*Figure 12: BLER performance of repetition-based and the extended deep polar codes with $N = 1024$ and $M = 1024 + 64 = 1088$, when SC decoding is applied.*


### Challenge 3: Non-Coherent Transmission

**Motivation**: Short packet scenarios suffer from significant pilot overhead

**Technical Approach**:
- Block-fading channels without CSI
- Code-splitting techniques
- Joint detection and decoding



## Conclusion

Polar codes represent a paradigm shift in channel coding, offering provable capacity achievement with practical implementability. The integration of advanced techniques - deep polar codes, SPP codes, and rate-matching - creates a comprehensive framework for next-generation wireless systems. These innovations enable polar codes to meet the stringent requirements of URLLC, support diverse applications from IoT to holographic communications, and provide the foundation for 6G wireless networks.

---

## Related Publications
1. **G. Choi** and N. Lee, "[Deep Polar Codes](https://ieeexplore.ieee.org/abstract/document/10462164)," in *IEEE Transactions on Communications*, vol. 72, no. 7, pp. 3842-3855, July 2024
2. **G. Choi** and N. Lee, "[Sparsely Pre-transformed Polar Codes for Low-Latency SCL Decoding](https://ieeexplore.ieee.org/abstract/document/10945422)," in *IEEE Transactions on Communications* (early access)
3. **G. Choi** and N. Lee, "[Rate-Matching Deep Polar Codes via Polar Coded Extension](https://arxiv.org/abs/2505.06867)," submitted to TCOM.


**Contact**: [geon.choi@postech.ac.kr](mailto:geon.choi@postech.ac.kr)

---

[← Back to Research](/research/)