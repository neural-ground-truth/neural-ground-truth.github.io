---
title: "The Reality of Low-Resource NLP"
description: "Why standard evaluation metrics fail for underrepresented languages."
pubDate: "2026-07-27"
heroImage: "../../assets/blog-placeholder-3.jpg"
---

<div class="tldr-box">
  <h4>TL;DR</h4>
  <ul>
    <li>Most LLMs suffer severe performance degradation on languages not well-represented in Common Crawl.</li>
    <li>Translation metrics like BLEU correlate poorly with human judgment on morphologically rich low-resource languages.</li>
  </ul>
</div>

When building models for low-resource languages, data scarcity is only half the battle. The other half is evaluation. How do we know our model is actually good when the benchmarks themselves are flawed or non-existent?

In this field note, we explore the paradox of evaluating models on Kinyarwanda and Swahili, and propose new, grounded methods for alignment.
