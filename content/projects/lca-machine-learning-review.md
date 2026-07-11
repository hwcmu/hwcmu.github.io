---
title: "Machine Learning for Life Cycle Assessment"
date: 2025-10-16
description: "A review and research-synthesis project mapping machine-learning methods to the four ISO phases of life cycle assessment."
tags: ["Sustainability", "Machine Learning", "LCA"]
weight: 3
url: "/projects/lca-machine-learning-review/"
aliases: ["/blogs/lca-ml-review/"]
---

![Framework mapping machine-learning methods to life cycle assessment phases](/images/lca-ml-framework.svg)

## Project Overview

Life cycle assessment (LCA) is a structured method for evaluating environmental impacts across a product or system lifecycle. In practice, it can be slowed by fragmented literature, manual data collection, missing inventory values, and computationally expensive impact models.

This project examined where machine learning can support the LCA workflow without treating it as a generic black box. The resulting framework maps specific methods to the four standard ISO phases and distinguishes workflow assistance from scientific interpretation.

## Research Approach

The work combined literature review, bibliometric analysis, and method synthesis. The central organizing question was not simply whether machine learning could be used in LCA, but where it could address a concrete workflow constraint.

1. **Goal and scope:** NLP can help screen literature and organize evidence relevant to system-boundary decisions, while the final boundary remains a research judgment.
2. **Life cycle inventory:** Statistical learning and probabilistic imputation can support missing-data estimation when uncertainty is carried forward explicitly.
3. **Impact assessment:** Surrogate models can approximate computationally intensive calculations when their domain of validity is defined and tested.
4. **Interpretation:** Model explanation and sensitivity analysis can help identify influential assumptions, but they do not replace causal or domain interpretation.

## Project Contribution

The main contribution is a phase-by-phase framework connecting machine-learning methods to specific LCA tasks, limitations, and research needs. It also provides a reproducible code base for the review's bibliometric workflow.

## Publication and Code

[Read the paper](https://doi.org/10.1371/journal.pclm.0000732) · [View the code](https://github.com/hwcmu/LCA-AI_review)
