---
title: "Stock-Based Monitoring of Global Power Transitions"
date: 2026-07-11
draft: false
description: "Built stock-flow diagnostics from power-plant records to separate renewable expansion, fossil-stock change, and future project pipelines."
topic: "Sustainability & Environmental Decision Systems"
tags: ["Energy Systems", "Sustainability", "Data Governance"]
projectType: "Research Project"
role: "Lead author · Framework design · Data analysis"
highlight:
  title: "Growth is not the same as replacement"
  text: "The central contribution is a metric that asks whether renewable additions coincide with fossil decline, rather than treating every new renewable asset as evidence of transition."
supportingHighlights:
  - title: "Plans and realized change stay separate"
    text: "Pipeline Tilt captures future orientation while Stock Substitution Intensity tracks what actually changed in the operating asset base."
  - title: "Missing retirement data becomes part of the result"
    text: "The workflow measures commissioning gaps and status-retirement conflicts instead of hiding uncertainty about asset exit."
doi: "10.1007/s40974-026-00425-8"
codeUrl: "https://github.com/hwcmu/stock-based-power-transition-monitoring"
---

![Stock-pipeline diagnostic space for global power-system transition](/images/fossil-persistence-stock-pipeline.png)

## Separate Build-Out from Stock Replacement

Renewable capacity additions are often treated as shorthand for power-sector decarbonization. I built a stock-based framework to ask whether renewable expansion coincides with a reduction in operating fossil capacity, while keeping planned development separate from realized change.

The work is based on my open-access paper, *A stock-based framework for monitoring fossil persistence and renewable expansion in global power systems*, published in *Energy, Ecology and Environment* in 2026.

Common transition indicators often blur together three different signals:

1. renewable capacity additions,
2. fossil-fuel operating-stock contraction, and
3. the forward-looking composition of project pipelines.

They are not interchangeable. A system can look greener because renewable projects are growing while its fossil operating stock remains unchanged.

## Make the Accounting Boundary Auditable

The analysis uses unit-level Global Integrated Power Tracker records from Global Energy Monitor to reconstruct the operating power-plant stock from 2010 to 2026. Each unit is classified by commissioning year, retirement evidence, technology, status, capacity, and region.

The core metric is **Stock Substitution Intensity (SSI)**:

```text
SSI = (renewable stock change - fossil stock change) / baseline renewable-plus-fossil stock
```

SSI measures stock-level structural reallocation in operating capacity. It does **not** directly measure generation displacement, emissions reduction, dispatch adequacy, or climate benefit.

The framework also compares SSI with **Pipeline Tilt (PT)**, the renewable share of announced, pre-construction, and under-construction project capacity. This separates realized stock change from forward-looking development intent.

## Renewable Expansion Can Coexist with Fossil Persistence

The relevant check is the joint movement of renewable and fossil operating stocks.

Project pipelines are broadly renewable-leaning, with a median PT of **0.828**, but realized stock change is much more uneven. Among subregions with positive SSI, **12 of 14** remain expansion-led: renewable additions coexist with non-declining fossil operating capacity.

Among the highest-ranking subregions by SSI, **80%** show renewable additions layered onto a fossil base that did not contract. East Asia illustrates the scale of the issue: renewable capacity increased by **786.7 GW**, while fossil operating capacity also increased by **311.7 GW** over the same period. Australia and New Zealand stand out as one of the few cases that looks closer to actual stock replacement, with a small fossil decline.

## The Hard Part: Seeing Exit

A major data challenge is that asset entry is much easier to observe than asset exit. New plants and project pipelines are often visible, but retirements and decommissioning dates are less consistently recorded.

In the reconstructed dataset, about **198,000 MW** of units lacked commissioning years, and another **73,000 MW** were marked as operating despite having retirement evidence. Together, these issues created a **3.16%** accounting gap.

This asymmetry is not just a cleaning problem. A monitoring system that observes additions more clearly than exits will tend to tell an optimistic story. The workflow therefore audits missing years, conflicting status and retirement evidence, and the capacity excluded by each decision.

## Why This Changes the Story

The project offers a compact way to read renewable build-out, fossil persistence, retirement evidence, and pipeline orientation together. Its main lesson is methodological as much as substantive: before using a clean-looking indicator to describe progress, ask what it can see and what it structurally misses.

These indicators can support infrastructure monitoring and questions for further analysis. They cannot establish emissions savings or operational reliability without generation, dispatch, and other relevant evidence. The [note on metrics and targets](/blogs/a-metric-can-be-valid-and-still-be-a-bad-target/) discusses why a valid measure still needs a bounded interpretation.
