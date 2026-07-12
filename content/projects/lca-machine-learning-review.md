---
title: "Machine Learning for Life Cycle Assessment"
date: 2025-10-16
description: "A review and research-synthesis project mapping machine-learning methods to the four ISO phases of life cycle assessment."
tags: ["Sustainability", "Machine Learning", "LCA"]
projectType: "Research Synthesis"
role: "Lead author · Review design · Bibliometric analysis"
highlight:
  title: "Organize machine learning by the decision it supports"
  text: "Instead of cataloging algorithms, the review maps each method to a specific life cycle assessment phase, workflow constraint, and interpretation boundary."
supportingHighlights:
  - title: "The evidence map is reproducible"
    text: "The bibliometric workflow preserves how the literature was organized rather than leaving the synthesis as an untraceable reading list."
  - title: "Judgment remains visible"
    text: "System boundaries, functional units, allocation, and final interpretation remain domain decisions even when machine learning assists the workflow."
doi: "10.1371/journal.pclm.0000732"
codeUrl: "https://github.com/hwcmu/LCA-AI_review"
url: "/projects/lca-machine-learning-review/"
aliases: ["/blogs/lca-ml-review/"]
---

![Framework mapping machine-learning methods to life cycle assessment phases](/images/lca-ml-framework.svg)

## Where Machine Learning Actually Helps

Life cycle assessment (LCA) evaluates environmental impacts across a product or system lifecycle. Its practical bottlenecks vary by phase: evidence can be fragmented, inventory data incomplete, impact calculations expensive, and final interpretations sensitive to assumptions.

This project asks where machine learning can address a specific LCA workflow problem without being treated as a generic replacement for domain judgment.

## Organizing the Evidence by Decision

The work combines literature review, bibliometric mapping, and phase-by-phase method synthesis. Papers were organized around the four standard LCA phases so that each machine-learning use case could be read in relation to the decision it supports.

| LCA phase | Potential machine-learning role | Important boundary |
| --- | --- | --- |
| Goal and scope | Literature screening and evidence organization | System boundaries remain a research judgment |
| Life cycle inventory | Missing-data estimation and probabilistic imputation | Uncertainty must be carried forward |
| Impact assessment | Surrogate modeling for expensive calculations | Validity depends on the training domain |
| Interpretation | Sensitivity analysis and model explanation | Explanation does not establish causality |

This structure shifts the review away from a list of algorithms and toward the analytical conditions under which a method is useful.

## The Most Useful Opportunities Come Earlier

The strongest opportunities are often not in replacing the final LCA model. They appear earlier in the workflow: organizing evidence, identifying data gaps, estimating missing inventory values, and reducing computational burden where repeated simulations are required.

The review also highlights recurring risks. A model can make a workflow faster while obscuring system boundaries, transferring poorly across product systems, or presenting imputed values with more certainty than the source data support.

## Where Human Judgment Still Matters

The accompanying repository preserves the bibliometric workflow and supporting materials used to organize the review. This makes the search-derived evidence map inspectable while keeping the conceptual synthesis tied to the published paper.

The project does not claim that machine learning resolves the normative choices built into LCA. Functional units, system boundaries, allocation rules, and interpretation still require domain expertise. The contribution is a clearer map of where computational methods can help and where human judgment remains irreducible.
