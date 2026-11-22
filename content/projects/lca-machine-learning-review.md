---
title: "Integrating Machine Learning into Life Cycle Assessment"
date: 2025-10-16
description: "Mapped ML methods to LCA workflow bottlenecks, with explicit limits on imputed inventories, surrogate predictions, and final interpretation."
topic: "Sustainability & Environmental Decision Systems"
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

## Where Can Estimated Data Help an LCA?

Life cycle assessment (LCA) often depends on incomplete inventories, inconsistent process descriptions, and computationally expensive impact calculations. Machine learning can help with these tasks, but an estimated value should not acquire the status of a measured observation simply because it fills a gap in a table.

In this review, I organized the literature around the four LCA phases. The aim was to connect methods to concrete workflow problems and identify what remains uncertain after a model is introduced.

## Organize the Evidence Around the Workflow

I combined literature review with a reproducible bibliometric search and keyword co-occurrence mapping. The accompanying repository preserves the bibliometric workflow; the published paper develops the phase-specific synthesis.

| LCA phase | Where ML can assist | What still needs checking |
| --- | --- | --- |
| Goal and scope | Literature screening and evidence organization | Functional units and system boundaries |
| Life cycle inventory | Missing-data estimation and probabilistic imputation | Training coverage and propagated uncertainty |
| Impact assessment | Surrogate and hybrid models for expensive calculations | Validity beyond the training domain |
| Interpretation | Sensitivity analysis and model explanation | Whether the explanation supports the intended decision |

This organization makes it possible to discuss a method's purpose and limitations without treating all applications of ML as equivalent.

## Prioritize the Data Bottleneck

The review identifies opportunities early in the workflow: organizing evidence, locating missing inventory information, and estimating inputs where data collection is difficult. Probabilistic approaches can make uncertainty in estimated inputs visible; surrogate models can reduce repeated computational work within an evaluated domain.

These are opportunities identified in a methodological review, rather than a benchmark establishing one algorithm's return on investment. Their usefulness depends on the process, data coverage, and validation design.

## Carry Uncertainty into the Final Claim

A filled inventory cell can conceal extrapolation to a technology, geography, or operating condition absent from the training data. A faster impact predictor can also make an analysis appear more certain than its input assumptions justify.

For a decision-facing LCA, estimated inputs should retain their provenance and uncertainty. Domain coverage and sensitivity to modeling choices need to remain visible alongside the final impact estimate.

Functional units, system boundaries, allocation, and interpretation remain research judgments. The contribution of this project is a workflow-based evidence map that helps analysts choose where ML can assist and what it leaves unresolved.
