---
title: "Fossil Persistence and Renewable Expansion in Global Power Systems"
date: 2026-07-11
draft: false
description: "A stock-based monitoring framework for distinguishing renewable build-out from actual fossil-fuel asset displacement in global power systems."
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

## A Different Way to Read the Transition

Renewable capacity additions are often treated as shorthand for power-sector decarbonization. This project asks a more uncomfortable question: when renewables are added, are fossil-fuel assets actually leaving the operating system, or are low-carbon assets simply being layered onto a still-persistent fossil base?

The work is based on my open-access paper, *A stock-based framework for monitoring fossil persistence and renewable expansion in global power systems*, published in *Energy, Ecology and Environment* in 2026.

Common transition indicators often blur together three different signals:

1. renewable capacity additions,
2. fossil-fuel operating-stock contraction, and
3. the forward-looking composition of project pipelines.

They are not interchangeable. A system can look greener because renewable projects are growing while its fossil operating stock remains unchanged.

## Following What Enters and Leaves

The analysis uses unit-level Global Integrated Power Tracker records to reconstruct the operating power-plant stock from 2010 to 2026. Each unit is classified by commissioning year, retirement evidence, technology, status, capacity, and region.

The core metric is **Stock Substitution Intensity (SSI)**:

```text
SSI = (renewable stock change - fossil stock change) / baseline renewable-plus-fossil stock
```

SSI measures stock-level structural reallocation in operating capacity. It does **not** directly measure generation displacement, emissions reduction, dispatch adequacy, or climate benefit.

The framework also compares SSI with **Pipeline Tilt (PT)**, the renewable share of announced, pre-construction, and under-construction project capacity. This separates realized stock change from forward-looking development intent.

## What the Numbers Reveal

> New renewable capacity does not automatically mean fossil-fuel capacity has been replaced.

Project pipelines are broadly renewable-leaning, with a median PT of **0.828**, but realized stock change is much more uneven. Among subregions with positive SSI, **12 of 14** remain expansion-led: renewable additions coexist with non-declining fossil operating capacity.

Among the highest-ranking subregions by SSI, **80%** show renewable additions layered onto a fossil base that did not contract. East Asia illustrates the scale of the issue: renewable capacity increased by **786.7 GW**, while fossil operating capacity also increased by **311.7 GW** over the same period. Australia and New Zealand stand out as one of the few cases that looks closer to actual stock replacement, with a small fossil decline.

## The Hard Part: Seeing Exit

A major data challenge is that asset entry is much easier to observe than asset exit. New plants and project pipelines are often visible, but retirements and decommissioning dates are less consistently recorded.

In the reconstructed dataset, about **198,000 MW** of units lacked commissioning years, and another **73,000 MW** were marked as operating despite having retirement evidence. Together, these issues created a **3.16%** accounting gap.

This asymmetry is not just a cleaning problem. A monitoring system that observes additions more clearly than exits will tend to tell an optimistic story. The workflow therefore audits missing years, conflicting status and retirement evidence, and the capacity excluded by each decision.

## Why This Changes the Story

The project offers a compact way to read renewable build-out, fossil persistence, retirement evidence, and pipeline orientation together. Its main lesson is methodological as much as substantive: before using a clean-looking indicator to describe progress, ask what it can see and what it structurally misses.

The world may be building more renewable capacity, but stock-level transition also depends on whether fossil assets are retiring, shrinking, or simply persisting in the background.
