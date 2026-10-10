# Reading List

## AI & Machine Learning

### Math and ML learning resources

- [CS4780/CS5780: Machine Learning for Intelligent Systems — Lecture Notes](https://www.cs.cornell.edu/courses/cs4780/2018fa/lectures/) — Kilian Weinberger, Cornell University, Fall 2018 · Course notes. Twenty-one lectures introduce core machine learning methods from k-nearest neighbors, logistic regression, optimization, and SVMs through kernels, Gaussian processes, trees, ensembles, and neural networks; the course also links to video lectures.
- [3Blue1Brown video source code](https://github.com/3b1b/videos) — 3Blue1Brown · Manim scene repository. Source code for the channel's explanatory math videos, organized by year; older scenes may require earlier Manim versions.
- [Deep-ML](https://www.deep-ml.com/) — Interactive ML practice platform. Browser-based Python problems with test feedback, guided paths, labs, projects, and math exercises spanning ML fundamentals, deep learning, computer vision, NLP, reinforcement learning, and CUDA.

### LLM architecture and training

- [The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/) — Jay Alammar, June 27, 2018 · Visual tutorial. Walks through the original encoder-decoder Transformer, including embeddings, positional encoding, self-attention, multi-head attention, and decoding.
- [22580: From GPT2 to Kimi3, Explained](https://x.com/waterloo_intern/status/2081762065392541951) — Ali, July 27, 2026 · Article. Traces the path from GPT-2 through linear attention and DeltaNet to Kimi K3, focusing on how language models store, update, and retrieve information.
- [GPT-6 Astra, Looped Transformers, and Hidden Reasoning](https://magazine.sebastianraschka.com/p/gpt-6-astra-looped-transformers-and) — Sebastian Raschka, September 9, 2026 · Article. Explains how looped transformers reuse weights across passes and examines unconfirmed claims about Astra's architecture and reasoning traces.
- [Modern LLM Notebook](https://github.com/walkinglabs/modern-llm-notebook) — WalkingLabs · Open course with PyTorch notebooks and scripts. Builds from tokenization and data preparation through small-model pretraining and supervised fine-tuning, with modules on MoE, tool calling, post-training, quantization, and inference. Some later recipes are still in development.
- [Why Diffusion Language Models Are the Future](https://dimitri.ml/posts/why-diffusion-language-models-are-the-future/) — Dimitri von Rütte, February 27, 2026 · Opinion essay. Argues that discrete diffusion LMs may benefit from flexible generation order and repeated training on limited data, with a focus on uniform diffusion that can revise tokens. Explores data-informed noise, learning when and how to revise, and adaptive sampling; the proposed large-scale advantages remain speculative.

### GPU systems and CUDA

- [How to Think About GPUs](https://jax-ml.github.io/scaling-book/gpus/) — Austin et al., August 18, 2025 · Book chapter. Explains NVIDIA GPU compute and memory, node and cross-node networking, collectives, and roofline limits for data, tensor, expert, and pipeline parallelism in LLM training.
- [How do CUDA Kernels work?](https://outcomeschool.com/blog/how-do-cuda-kernels-work) — Amit Shekhar, September 29, 2026 · Introductory article. Explains threads, blocks, and grids with a vector-add kernel, then covers host/device memory, SMs and warps, memory hierarchy, and when GPU execution helps or hurts.
- [CUDA from zero to hero #1](https://x.com/goyal__pramod/status/2103565642800431533) — Pramod Goyal, September 25, 2026 · [X article](https://x.com/i/article/2103559794980470785). Introductory notes on GPU hardware and CUDA execution, followed by a naive matrix-multiplication kernel that illustrates row-major storage, thread indexing, and grid sizing. The author plans to extend the series with performance bottlenecks and optimization.

### LLM inference and serving

- [Inference Engineering](https://x.com/techNmak/status/2107678022094790933) — Tech with Mak, October 7, 2026 · X explainer and infographic. Surveys prefill versus decode, KV-cache and attention optimizations, batching and scheduling, quantization, speculative decoding, and multi-GPU serving. Connects TTFT, inter-token latency, throughput, and goodput to practical bottleneck diagnosis; a conceptual overview rather than a benchmark.
- [A Visual Guide to Quantization](https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-quantization) — Maarten Grootendorst, July 22, 2024 · Illustrated tutorial. Builds intuition for numeric formats, symmetric and asymmetric scaling, post-training quantization, GGUF, quantization-aware training, and low-bit LLM methods through extensive visuals.
- [第 8 章 推理优化](https://github.com/bojieli/ai-infra-book/blob/main/manuscripts/08-%E6%8E%A8%E7%90%86%E4%BC%98%E5%8C%96.md) — 《AI Infra Book》书稿章节。分析批处理与请求调度、KV 缓存分页和前缀复用、压缩与卸载、推测解码，以及延迟、吞吐和答案质量之间的取舍。
- [AirLLM](https://github.com/lyogavin/airllm) — Gavin Li · Open-source inference library. Splits model checkpoints into per-layer files, loads each module onto the GPU just before execution, and releases it afterward. This lowers VRAM requirements but requires substantial disk space and repeated weight transfers; optional compression and adapter training are also supported.
- [NVIDIA Model Optimizer](https://github.com/NVIDIA/Model-Optimizer) — NVIDIA · Open-source library. Combines quantization, pruning, distillation, sparsity, and speculative decoding to prepare smaller or faster models; exports optimized checkpoints for inference frameworks including TensorRT-LLM, vLLM, and SGLang.
- [Understanding Quantization](https://drive.google.com/file/d/1JPWFc9lArJ-viyqf4ZkXpxF-jhYNkK9q/view) — @techNmak · Understanding AI Series, Handbook 10 · PDF. Explains scales and zero-points, quantization error and granularity, PTQ and QAT, and weight, activation, and KV-cache quantization. Compares methods including GPTQ, AWQ, NF4/QLoRA, and FP8; runtime speedups depend on compatible kernels and hardware, not bit-width alone.
- [MoE inference engineering, clearly explained](https://x.com/_avichawla/status/2100876555409039605) — Avi Chawla, September 2026 · Article ([full text on the author's site](https://www.dailydoseofds.com/p/moe-inference-engineering-clearly-explained/)). Follows token routing, expert batching, grouped GEMM, expert parallelism, GPU placement, and load imbalance. Separates activated computation, resident model weights, and transferred activations when diagnosing serving bottlenecks.
- [vLLM's beautiful architecture, explained](https://x.com/attharrva15/status/2103918757446062165) — Atharva, September 26, 2026 · [X article](https://x.com/i/article/2103822119595548672). An introductory account of prefill versus decode, growing KV caches, and how PagedAttention, continuous batching, and scheduling help serve requests of different lengths efficiently.
- [KV, Prefix, Prompt and Semantic Caching in LLMs, clearly explained](https://x.com/_avichawla/status/2093265776266637739) — Avi Chawla, August 28, 2026 · [X article](https://x.com/i/article/2093210840468189184). Compares four caching layers by what they store and when they can be reused, with code examples and production pitfalls. Explains why exact prefix reuse can fail and why embedding-based semantic cache hits require correctness checks.

### LLM memory and knowledge integration

- [MeMo: Memory as a Model](https://arxiv.org/abs/2605.15156) — Quek et al., May 2026 · Preprint. Trains a dedicated memory model on questions and answers synthesized from a corpus while keeping the answering LLM frozen; at inference, the LLM queries that model through targeted sub-questions. Evaluated on BrowseComp-Plus, NarrativeQA, and MuSiQue, including tests with distractor documents. Each new corpus requires upfront training, and memory capacity is limited by the dedicated model's size.

### World models and spatial intelligence

- [CIS 6280 · World Models — Resources](https://www.cis.upenn.edu/~cis6280/#resources) — University of Pennsylvania, Fall 2026 · Course resource collection. Curated essays, tutorials, talks, and system demos on world models, alongside a course covering reinforcement learning, video and 3D, robotics, and agents.
- [空间记忆：智能系统缺失的认知底座](https://luliu.me/posts/kong-jian-ji-yi-zhi-neng-xi-tong-que-shi-de-ren-zhi-di-zuo/) — 刘露、张彦峰，2026-05-05 · 长文。主张物理世界智能需要持续维护可查询、可校准、可追溯的时空状态，梳理认知地图、感知—认知—记忆架构、技术路线与评测缺口。

### Mechanistic interpretability and neural geometry

- [Revisiting the Platonic Representation Hypothesis: An Aristotelian View](https://arxiv.org/pdf/2602.14486) — Gröger et al., 2026 · ICML paper. Shows that model width and depth can inflate representation-similarity scores; after calibration, apparent global convergence largely disappears while cross-modal local-neighborhood agreement remains.
- [The World Inside Neural Networks](https://www.goodfire.com/research/the-world-inside-neural-networks) — Geiger et al., May 7, 2026 · Research essay. Introduces neural geometry and shows how following curved representation manifolds can make interventions in a model more precise.
  - **我的理解：** Activation space 中存在弯曲的 manifold。线性近似仍然有用，这解释了 LRH、SAE 和简单加减式 steering 为什么能取得一些效果，但它们的成功有边界。若想更深入地理解 activation 并更可靠地控制模型，至少要弄清线性近似何时有效、何时失效；steering 的系数 α 过大时模型表现变差，也可以从这个角度理解。
  - **评价与后续：** 这篇文章更多是在梳理已有论文中的观点，创新性暂时不算强，可以当作科普。继续关注 Goodfire 的后续工作，看看是否会提出更有意思的新方法。
- [Uncovering Neural Geometry in Vision Models With Block-Sparse Featurizers](https://www.goodfire.com/research/bsf-vision) — Fel et al., July 7, 2026 · Research article. Introduces block-sparse featurizers to find multidimensional concepts in vision-model activations and use them for fine-grained steering.
- [Modular Cognitive Architecture Emerges in Large Language Models](https://pengrui-han.github.io/LLM_Modularity_Page/) — Han et al., 2026 · Preprint and project page. Uses attribution patching across 46 language, formal, physical, and social reasoning tasks, then neuron ablations, to study functional specialization in LLMs.
- [Beneath the Surface of Chains-of-Thought: A Mechanistic Interpretation of Reasoning Operations in LLMs](https://arxiv.org/pdf/2609.04753) — Jeong et al., September 2026 · EMNLP paper. Studies how labeled reasoning operations appear in hidden representations of chain-of-thought traces; finds the clearest separation in middle layers and tests how prior context shapes these signals.

### AI safety and monitoring

- [The fragile foundations of CoT monitoring](https://web.stanford.edu/~cgpotts/blog/cot/) — Christopher Potts, July 27, 2026 (updated August 9) · Workshop reflection. Argues that chain-of-thought is useful but fragile as a safety signal because models may compute without verbalizing it or produce unfaithful reasoning traces. Advocates studying internal states and action records; the update questions whether CoT would have added useful signal in a cyber incident.

### Reinforcement learning and post-training

- [Hands-On Modern RL](https://github.com/walkinglabs/hands-on-modern-rl) — WalkingLabs · Open course and book. A practical path from MDPs, DQN, and PPO to RLHF, DPO, GRPO, RLVR, and agentic RL, with code and notebooks. The maintainers note that some material is still being reviewed.
- [On-Policy Self-Distillation without Any Supervision](https://alphaxiv.org/abs/2608.06296) — Li et al., August 2026 · [Preprint](https://arxiv.org/abs/2608.06296). Introduces u-OPSD: majority voting over a model's own rollouts creates a pseudo-solution, which guides distillation on disagreeing completions without external labels or a stronger teacher. Reports improvements on Qwen3 mathematical reasoning benchmarks; the approach currently relies on answers that can be extracted and compared.

### RL training infrastructure

- [RL is Everything, Everywhere, All at Once](https://skypilot.ai/blog/rl-everything) — Ishan Kaul, September 10, 2026 · Blog post. Surveys the infrastructure behind large RL post-training runs: rollout inference, sandboxes, distributed training, weight synchronization, scheduling, and failure recovery.
- [The ultimate guide to multi-harness RL](https://huggingface.co/spaces/FineEnvs/multi-harness-rl#introduction) — Kolavi et al., October 1, 2026 · Interactive guide and experiment. Trains coding agents across existing harnesses using an OpenEnv capture proxy for exact tokens and log probabilities, Harbor for tasks and sandboxes, and TRL for optimization. Reports LFM2.5-2.6B pass@1 rising from 42.2% to 54.2% across four harnesses on SmolDataEnvs; the study uses one task family and one seed per setup.

### Agent infrastructure and harness engineering

- [The Next Scaling Problem](https://tetral.ai/blog/the-next-scaling-problem/) — Yang Li, September 6, 2026 · Blog post. Describes a cloud agent architecture that separates the durable agent runtime and history from disposable execution environments so each can scale and recover independently.
- [Learn Harness Engineering](https://walkinglabs.github.io/learn-harness-engineering/en/) — WalkingLabs · Open course. Lectures, projects, and templates for building reliable coding-agent harnesses, covering environment design, state across sessions, rules, verification, and observability.

## Software engineering

### System design and distributed systems

- [System Design Notes](https://github.com/liquidslr/system-design-notes) — liquidslr · Open notes based on Alex Xu's *System Design Interview* volumes 1 and 2. Covers scaling and back-of-the-envelope estimation, then design cases such as rate limiting, consistent hashing, key-value stores, message queues, object storage, and payments. The notes are a work in progress.
