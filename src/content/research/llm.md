---
title: "Deep Learning & LLMs"
description: "A comprehensive academic roadmap from foundational neural networks to Large Language Models, modeled after CMU 11-785."
pubDate: "2026-07-30"
---

Large Language Models are the foundational reasoning engines for modern AI, but they do not exist in a vacuum. To understand the intricacies of modern transformers and LLMs, one must understand the architectural evolution that led to them.

This roadmap outlines a structured, 4-phase academic progression for Deep Learning, establishing a rigorous baseline of knowledge before diving into cutting-edge LLM research.

---

### Phase 1: Foundations of Deep Learning
*The mathematical engine of all modern AI.*

Before analyzing massive language models, the baseline mathematics of neural optimization must be mastered.
- **The Perceptron & MLPs:** Understanding linear separability and the necessity of hidden layers in Multi-Layer Perceptrons.
- **Forward Propagation & Empirical Risk:** Formulating the loss landscape.
- **Backpropagation:** The definitive gradient descent method that allows multi-layer networks to learn internal representations, established in *Learning representations by back-propagating errors* ([Rumelhart, Hinton, & Williams, 1986](https://www.nature.com/articles/323533a0)).
- **Optimization & Regularization:** Navigating the loss landscape using SGD, Momentum, and Adam, while preventing overfitting via Dropout and Batch Normalization.

### Phase 2: Spatial & Temporal Modeling
*Architectures designed to exploit the structural inductive biases of data.*

- **Spatial (CNNs):** Convolutional Neural Networks exploit spatial locality. Key concepts include receptive fields, translational invariance, and overcoming depth degradation via residual connections (e.g., ResNets).
- **Temporal (RNNs):** Recurrent Neural Networks process sequential data but suffer from vanishing gradients. This was famously solved by the Long Short-Term Memory architecture, introduced in *Long Short-Term Memory* ([Hochreiter & Schmidhuber, 1997](https://doi.org/10.1162/neco.1997.9.8.1735)), which introduced gating mechanisms to preserve long-range dependencies.

### Phase 3: Sequence-to-Sequence & Attention
*The paradigm shift away from recurrence.*

- **The Information Bottleneck:** Early Seq2Seq models forced entire sequences into a single fixed-length context vector, severely degrading performance on long inputs.
- **Attention Mechanisms:** The breakthrough solution was allowing the decoder to "look back" at specific parts of the encoded sequence at each time step. The foundational paper demonstrating this alignment is *Neural Machine Translation by Jointly Learning to Align and Translate* ([Bahdanau et al., 2014](https://arxiv.org/abs/1409.0473)).

---

### Phase 4: Transformers & LLMs (The Frontier)
*The architecture that scaled AI to superhuman levels.*

- **The Transformer:** Recurrence was completely abandoned in favor of massive parallelization via Self-Attention in the seminal paper *Attention Is All You Need* ([Vaswani et al., 2017](https://arxiv.org/abs/1706.03762)).
- **LLM Pretraining & Scaling Laws:** The shift from encoder-decoder architectures to massive causal (decoder-only) models like the GPT series, trained on next-token prediction at Internet-scale.
- **Efficiency & Deployment:** Optimizing massive parameters using Mixture of Experts (MoE), rotary positional embeddings (RoPE), and advanced quantization (AWQ/GPTQ).
- **Alignment:** Moving beyond raw token prediction into agentic planning and human-aligned responses via Reinforcement Learning from Human Feedback (RLHF) and Direct Preference Optimization (DPO).

### Our Engineering Focus
Our ongoing research builds directly upon **Phase 4**. We focus specifically on:
- Exploring emergent reasoning capabilities in highly-distilled, significantly smaller models.
- Improving multilingual reasoning and zero-shot transfer capabilities for underrepresented African languages.
