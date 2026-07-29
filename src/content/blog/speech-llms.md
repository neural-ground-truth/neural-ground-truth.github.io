---
title: "Comparing Speech LLM Architectures"
description: "A Raschka-style side-by-side comparison of modern speech language models."
pubDate: "2026-07-28"
heroImage: "../../assets/blog-placeholder-2.jpg"
---

<div class="tldr-box">
  <h4>TL;DR</h4>
  <ul>
    <li>Speech LLMs typically discretize audio into tokens using models like EnCodec before feeding them to a standard transformer.</li>
    <li>Direct speech-to-text models bypass acoustic modeling layers and learn to align speech embeddings with text token embeddings.</li>
  </ul>
</div>

Over the last 18 months, there has been an explosion of research applying LLM architectures directly to audio streams. 

### Continuous vs Discrete
A major architectural fork in the road is how we represent audio. Do we keep it continuous and project the representations using adapters, or do we discretize it into tokens (AudioLM, VALL-E) and treat it exactly like text?

In this post, we'll compare the throughput, quality, and training stability of both approaches.
