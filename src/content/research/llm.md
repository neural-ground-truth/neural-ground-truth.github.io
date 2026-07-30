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

- **The Transformer:** Recurrence was completely abandoned in favor of massive parallelization via Self-Attention in the seminal paper *Attention Is All You Need* ([Vaswani et al., 2017](https://arxiv.org/abs/1706.03762)). For a definitive visual intuition of this architecture, see *The Illustrated Transformer* [^2].

[^2]: Alammar, J. (2018). "The Illustrated Transformer." [jalammar.github.io](https://jalammar.github.io/illustrated-transformer/).
- **LLM Pretraining & Scaling Laws:** The shift from encoder-decoder architectures to massive causal (decoder-only) models like the GPT series, trained on next-token prediction at Internet-scale.
- **Efficiency & Deployment:** Optimizing massive parameters using Mixture of Experts (MoE), rotary positional embeddings (RoPE), and advanced quantization (AWQ/GPTQ).
- **Alignment:** Moving beyond raw token prediction into agentic planning and human-aligned responses via Reinforcement Learning from Human Feedback (RLHF) and Direct Preference Optimization (DPO).

### Phase 5: Systems, Infrastructure, & Scaling
*The engineering reality of deploying massive models.*

Theory alone cannot train a trillion-parameter model. As outlined in the **CMU 11-868 (Large Language Model Systems)** curriculum, deploying state-of-the-art AI requires overcoming severe memory and bandwidth bottlenecks across massive GPU clusters.
- **Parallelism:** The sheer size of modern LLMs requires splitting them across hundreds of GPUs. The definitive framework for 3D Parallelism (Data, Tensor, and Pipeline parallelism) was established in *Megatron-LM* [^1].

[^1]: Shoeybi, M., et al. (2019). "Megatron-LM: Training Multi-Billion Parameter Language Models Using Model Parallelism." arXiv preprint arXiv:1909.08053.
- **Memory Optimization:** To prevent Out-Of-Memory (OOM) errors during distributed training, gradients and optimizer states must be sharded across GPUs, famously solved by the Zero Redundancy Optimizer in *ZeRO* ([Rajbhandari et al., 2020](https://arxiv.org/abs/1910.02054)).
- **Compute Efficiency:** Standard attention is bottlenecked by GPU memory reads/writes. Fusing operations to keep data on the SRAM was revolutionized by *FlashAttention* ([Dao et al., 2022](https://arxiv.org/abs/2205.14135)).
- **Serving & Inference:** Production serving requires extreme throughput. Solving memory fragmentation in the KV cache was achieved via *PagedAttention*, the engine behind the open-source *vLLM* engine ([Kwon et al., SOSP 2023](https://arxiv.org/abs/2309.06180)).

### Our Engineering Focus
Our ongoing research builds directly upon **Phase 4 and Phase 5**. We focus specifically on:
- Exploring emergent reasoning capabilities in highly-distilled, significantly smaller models to bypass heavy infrastructure bottlenecks.
- Improving multilingual reasoning and zero-shot transfer capabilities for low-resource languages, optimizing for edge deployment.
