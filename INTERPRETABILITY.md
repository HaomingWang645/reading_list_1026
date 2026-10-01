# Interpretability and Neural Geometry

A visual reading list on how models represent space, time, concepts, and reasoning. Selected entries include a short takeaway and a figure from the original paper or post. Select a figure to see the original at full size.

[Back to the main reading list](README.md)

## [The World Inside Neural Networks](https://www.goodfire.com/research/the-world-inside-neural-networks)

*Geiger et al., May 7, 2026 · Research essay*

Introduces neural geometry and shows how following curved representation manifolds can make interventions in a model more precise.

<p align="center">
  <a href="https://static.goodfire.ai/neural-geometry-agenda/neural-geometry-opengraph.webp"><img src="assets/interpretability/neural-geometry.webp" alt="Seven colorful neural-representation manifolds labeled geography, days of the week, formality, temperature, color, years, and age." width="720"></a><br>
  <sub><em>Examples of geometric structure in model representations.</em> · <a href="https://static.goodfire.ai/neural-geometry-agenda/neural-geometry-opengraph.webp">Original figure</a></sub>
</p>

> **Reading note.** Activation space contains curved manifolds. Linear approximations remain useful, which helps explain why the linear representation hypothesis, sparse autoencoders, and simple additive steering can work, but their success has limits. To understand and control activations more reliably, we need to know when those approximations hold. Degradation at large steering strengths can also be viewed through this lens.
>
> **Follow-up.** This essay mostly synthesizes ideas from earlier papers, so its novelty seems limited for now. It works well as an introduction; follow Goodfire's later work for new methods.

## Interpreting Spatial Representations in VLM

### [S-Space: Exploring Spatial Workspace in Multimodal Models](https://mirros.ai/report/s-space.pdf)

*MirroS, September 2026 · Technical report ([interactive post](https://mirros.ai/blog/s-space))*

Studies an internal spatial subspace in vision-language models: linear readouts from object-token activations track viewer-centered horizontal, vertical, and distance coordinates. Interventions on these coordinates change spatial judgments, and an external coordinate transformation can outperform the model's own perspective-taking answers.

<p align="center">
  <a href="https://mirros.ai/media/research/s-space/figure-02/figure-02.svg"><img src="assets/interpretability/s-space.svg" alt="The proposed S-Space workspace connects visual perception, internal spatial representation, and downstream answers." width="680"></a><br>
  <sub><em>The proposed spatial workspace and earlier evidence from 2D grid worlds.</em> · <a href="https://mirros.ai/media/research/s-space/figure-02/figure-02.svg">Original figure</a></sub>
</p>

- [What, Where, and How: Probing Spatiotemporal Representations in Video Foundation Models](https://arxiv.org/abs/2609.01551)
- [SeeSE3: Emergence of 3D Space in Vision Features](https://arxiv.org/abs/2607.14228)

## Other Interesting Recent Works on Interpretability

### [Beneath the Surface of Chains-of-Thought: A Mechanistic Interpretation of Reasoning Operations in LLMs](https://arxiv.org/abs/2609.04753)

*Jeong et al., September 2026 · EMNLP paper*

Studies how labeled reasoning operations appear in hidden representations of chain-of-thought traces; finds the clearest separation in middle layers and tests how prior context shapes these signals.

<p align="center">
  <a href="https://arxiv.org/html/2609.04753v1/teaser.png"><img src="assets/interpretability/reasoning-operations.png" alt="Reasoning-operation vector scores highlight different parts of a chain-of-thought trace." width="760"></a><br>
  <sub><em>Reasoning-operation scores across a chain-of-thought trace.</em> · <a href="https://arxiv.org/html/2609.04753v1/teaser.png">Original figure</a></sub>
</p>

### [Temporal Context Reinstatement Drives Episodic-Like Order Memory in Long-Context Language Models](https://arxiv.org/abs/2607.22575)

*Pink et al., 2026 · ICML paper*

Tests whether long-context LLMs can judge which of two passages came first and compares their distance effect with human order memory. Mechanistic analyses identify a one-dimensional temporal code reinstated at retrieval by a particular attention head; removing that direction weakens order judgments.

<p align="center">
  <a href="https://arxiv.org/html/2607.22575v1/retrieval-temporal-information.png"><img src="assets/interpretability/temporal-context.png" alt="Retrieval-phase temporal information by attention head in two Llama models." width="690"></a><br>
  <sub><em>Retrieval-phase temporal information across attention heads.</em> · <a href="https://arxiv.org/html/2607.22575v1/retrieval-temporal-information.png">Original figure</a></sub>
</p>

### [Revisiting the Platonic Representation Hypothesis: An Aristotelian View](https://arxiv.org/abs/2602.14486)

*Gröger et al., 2026 · ICML paper*

Shows that model width and depth can inflate representation-similarity scores; after calibration, apparent global convergence largely disappears while cross-modal local-neighborhood agreement remains.

<p align="center">
  <a href="https://arxiv.org/html/2602.14486v2/null-cali-v8.png"><img src="assets/interpretability/platonic-representation.png" alt="Figure 1: Local neighborhood relationships can align across different representation spaces." width="610"></a><br>
  <sub><em>Local neighborhoods can align across different representation spaces.</em> · <a href="https://arxiv.org/html/2602.14486v2/null-cali-v8.png">Original figure</a></sub>
</p>

## [SpatialLadder: Progressive Training for Spatial Reasoning in Vision-Language Models](https://arxiv.org/pdf/2510.08531)

*Li et al., October 2025 · Paper*

Introduces SpatialLadder-26k, a 26,610-example dataset spanning object localization and spatial tasks using single images, multiple views, and video. Its three-stage training recipe first grounds objects, then teaches spatial relationships, and finally uses reinforcement learning with verifiable rewards for more complex reasoning. The authors report improved spatial-benchmark performance for their 3B-parameter model.

<p align="center">
  <a href="https://arxiv.org/html/2510.08531v1/framework.png"><img src="assets/interpretability/spatialladder.png" alt="SpatialLadder&#x27;s three training stages: object grounding, spatial understanding, and reinforcement learning." width="760"></a><br>
  <sub><em>The three training stages, from object grounding to spatial reasoning.</em> · <a href="https://arxiv.org/html/2510.08531v1/framework.png">Original figure</a></sub>
</p>

## [Modular Cognitive Architecture Emerges in Large Language Models](https://pengrui-han.github.io/LLM_Modularity_Page/)

*Han et al., 2026 · Preprint and project page*

Uses attribution patching across 46 language, formal, physical, and social reasoning tasks, then neuron ablations, to study functional specialization in LLMs.

<p align="center">
  <a href="https://pengrui-han.github.io/LLM_Modularity_Page/assets/figures/ablation_within_vs_across_3bar.png"><img src="assets/interpretability/modular-cognitive-architecture.png" alt="Bar chart of accuracy drops after within-domain and cross-domain neuron ablations." width="690"></a><br>
  <sub><em>Within-domain neuron ablations affect accuracy more than cross-domain ablations.</em> · <a href="https://pengrui-han.github.io/LLM_Modularity_Page/assets/figures/ablation_within_vs_across_3bar.png">Original figure</a></sub>
</p>

## [Uncovering Neural Geometry in Vision Models With Block-Sparse Featurizers](https://www.goodfire.com/research/bsf-vision)

*Fel et al., July 7, 2026 · Research article*

Introduces block-sparse featurizers to find multidimensional concepts in vision-model activations and use them for fine-grained steering.

<p align="center">
  <a href="https://static.goodfire.ai/bsf-vision/arches-hands.webp"><img src="assets/interpretability/block-sparse-featurizers.webp" alt="Examples of image regions associated with positions in two learned feature subspaces." width="730"></a><br>
  <sub><em>Image regions and positions in learned multidimensional feature blocks.</em> · <a href="https://static.goodfire.ai/bsf-vision/arches-hands.webp">Original figure</a></sub>
</p>
