# Reading List

## AI & Machine Learning

### LLM architecture

- [22580: From GPT2 to Kimi3, Explained](https://x.com/waterloo_intern/status/2081762065392541951) — Ali, July 27, 2026 · Article. Traces the path from GPT-2 through linear attention and DeltaNet to Kimi K3, focusing on how language models store, update, and retrieve information.

### Mechanistic interpretability and neural geometry

- [The World Inside Neural Networks](https://www.goodfire.com/research/the-world-inside-neural-networks) — Geiger et al., May 7, 2026 · Research essay. Introduces neural geometry and shows how following curved representation manifolds can make interventions in a model more precise.
  - **我的理解：** Activation space 中存在弯曲的 manifold。线性近似仍然有用，这解释了 LRH、SAE 和简单加减式 steering 为什么能取得一些效果，但它们的成功有边界。若想更深入地理解 activation 并更可靠地控制模型，至少要弄清线性近似何时有效、何时失效；steering 的系数 α 过大时模型表现变差，也可以从这个角度理解。
  - **评价与后续：** 这篇文章更多是在梳理已有论文中的观点，创新性暂时不算强，可以当作科普。继续关注 Goodfire 的后续工作，看看是否会提出更有意思的新方法。
- [Uncovering Neural Geometry in Vision Models With Block-Sparse Featurizers](https://www.goodfire.com/research/bsf-vision) — Fel et al., July 7, 2026 · Research article. Introduces block-sparse featurizers to find multidimensional concepts in vision-model activations and use them for fine-grained steering.
