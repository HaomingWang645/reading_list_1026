# Reading List

## AI & Machine Learning

### LLM architecture

- [22580: From GPT2 to Kimi3, Explained](https://x.com/waterloo_intern/status/2081762065392541951) — Ali, July 27, 2026 · Article. Traces the path from GPT-2 through linear attention and DeltaNet to Kimi K3, focusing on how language models store, update, and retrieve information.
- [GPT-6 Astra, Looped Transformers, and Hidden Reasoning](https://magazine.sebastianraschka.com/p/gpt-6-astra-looped-transformers-and) — Sebastian Raschka, September 9, 2026 · Article. Explains how looped transformers reuse weights across passes and examines unconfirmed claims about Astra's architecture and reasoning traces.

### LLM inference and serving

- [第 8 章 推理优化](https://github.com/bojieli/ai-infra-book/blob/main/manuscripts/08-%E6%8E%A8%E7%90%86%E4%BC%98%E5%8C%96.md) — 《AI Infra Book》书稿章节。分析批处理与请求调度、KV 缓存分页和前缀复用、压缩与卸载、推测解码，以及延迟、吞吐和答案质量之间的取舍。
- [AirLLM](https://github.com/lyogavin/airllm) — Gavin Li · Open-source inference library. Splits model checkpoints into per-layer files, loads each module onto the GPU just before execution, and releases it afterward. This lowers VRAM requirements but requires substantial disk space and repeated weight transfers; optional compression and adapter training are also supported.

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

### Reinforcement learning and post-training

- [Hands-On Modern RL](https://github.com/walkinglabs/hands-on-modern-rl) — WalkingLabs · Open course and book. A practical path from MDPs, DQN, and PPO to RLHF, DPO, GRPO, RLVR, and agentic RL, with code and notebooks. The maintainers note that some material is still being reviewed.

### RL training infrastructure

- [RL is Everything, Everywhere, All at Once](https://skypilot.ai/blog/rl-everything) — Ishan Kaul, September 10, 2026 · Blog post. Surveys the infrastructure behind large RL post-training runs: rollout inference, sandboxes, distributed training, weight synchronization, scheduling, and failure recovery.

### Agent infrastructure

- [The Next Scaling Problem](https://tetral.ai/blog/the-next-scaling-problem/) — Yang Li, September 6, 2026 · Blog post. Describes a cloud agent architecture that separates the durable agent runtime and history from disposable execution environments so each can scale and recover independently.
