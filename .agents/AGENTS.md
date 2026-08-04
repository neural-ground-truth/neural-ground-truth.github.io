# Project Directives: Neural Ground Truth

## The "Lil'Log" Standard for Content Generation
When asked to generate blog posts, research roadmaps, paper analyses, or technical explanations for this project, agents MUST adhere to an extreme level of academic and technical rigor, benchmarked against Lilian Weng's "Lil'Log" (https://lilianweng.github.io/). 

Do NOT provide surface-level, high-level, or purely conversational summaries.

### Requirements for all technical content:
1. **Mathematical Rigor:** Always include the underlying mathematics, formulas, and loss functions (using KaTeX/MathJax formatting) rather than just describing what an algorithm does in English. 
2. **Empirical Analysis:** Reference specific charts, scaling laws, compute-optimal frontiers, and data sizes (e.g., parameter counts, token budgets, FLOPs) when discussing architectures.
3. **Algorithmic Breakdowns:** Explain *how* architectures work at a tensor/matrix level. 
4. **Heavy Citations:** Always use extensive inline Markdown footnotes (e.g., `[^1]`) to cite the seminal papers (e.g., Vaswani, Kaplan, Hoffmann) that established the concepts being discussed.
5. **Tone:** Academic, highly technical, and objective.
