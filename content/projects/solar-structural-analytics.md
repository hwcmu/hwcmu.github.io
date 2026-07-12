---
title: "Beyond Megawatts: Structural Analytics for Global Utility-Scale Solar"
date: 2026-07-12
draft: false
description: "A global infrastructure data analysis project that turns nearly 100,000 solar project records into interpretable national development typologies."
tags: ["Structural Analytics", "Network Science", "Infrastructure Data"]
projectType: "Research Project"
role: "Lead author · Representation design · Network analysis · Validation"
doi: "10.1007/s40974-026-00428-5"
codeUrl: "https://github.com/hwcmu/global-solar-project-ecologies"
---

![Capacity-based national camps in global utility-scale solar development](/images/solar-capacity-camps-map.png)

## Project Overview

Two countries can report the same amount of solar capacity. But are they building solar in the same way?

That question drives this project. Aggregate megawatt rankings can tell us which countries are large, but they often hide the internal structure of national solar development. One country may be built around many already-operating small and mid-sized projects. Another may appear equally large because a small number of very large projects sit in the announced or pre-construction pipeline.

This project reframes utility-scale solar development as a structural data problem: not just **how many megawatts** a country reports, but **how its solar portfolio is actually composed**.

The work is based on my open-access paper, *Beyond megawatts: Structural configurations and project ecologies in global utility-scale solar*, published in *Energy, Ecology and Environment* in 2026.

## The Core Problem

Traditional country comparisons compress solar development into aggregate volume: total capacity, number of projects, or rank. Those metrics are useful, but they flatten important differences.

The project asks a more diagnostic question:

> Similar megawatts can represent very different development structures.

A country dominated by operating 5-50 MW projects is not structurally equivalent to a country dominated by announced 500+ MW projects, even if their total capacity looks similar. The first reflects a more distributed operating base; the second may reflect concentrated future ambition that has not yet materialized.

The analytical goal was therefore to move from a country-level total to a country-level structure.

## Data Scale

The retained analytical scope included:

- **98,942** phase-level utility-scale solar project records,
- **94** countries,
- **3.57 TW** of retained utility-scale solar capacity,
- **16** predefined size-status modes, and
- **2** complementary analytical views: capacity and count.

The source data came from the February 2026 release of the Global Solar Power Tracker. The analysis retained operating, construction, pre-construction, and announced project phases, then represented each country by the internal composition of its project portfolio.

## Representation Design

The key design move was to represent each country through a clean 4 x 4 structure:

| Dimension | Categories |
| --- | --- |
| Project size | 1-5 MW, 5-50 MW, 50-500 MW, 500+ MW |
| Project status | operating, construction, pre-construction, announced |

Crossing these two dimensions produces **16 size-status modes**. Each country becomes a normalized profile across those modes.

That turns the question from:

> How much solar does this country have?

into:

> What kind of solar development structure does this country have?

This is the main representation-design contribution of the project. It makes countries comparable by internal structure rather than by sheer scale.

## Why Normalization Matters

![Structural normalization contrast for country projections](/images/solar-structural-normalization.png)

Without normalization, the similarity space is dominated by a few very large countries. Row normalization shifts the comparison from absolute national volume to within-country portfolio structure.

In the raw projection, the top five countries accounted for **0.665** of total capacity-projection strength. After row normalization, that share fell to **0.093**. In the count projection, the top-five share similarly fell from **0.614** to **0.084**.

That shift matters because the project is not trying to re-rank countries by size. It is trying to compare how countries organize their solar development portfolios.

## Two Views, Two Worlds

The project builds two complementary views of the same global solar system.

**Capacity view: system weight**  
This view is sensitive to where the megawatts are concentrated. It highlights large projects, mega-project pipelines, and system-level infrastructure weight.

**Count view: project ecology**  
This view is sensitive to project frequency. It shows whether a country is made up of many small projects, a mixture of mid-sized projects, or a sparse portfolio dominated by a few large entries.

The result is not one universal classification. It is a pair of related but non-interchangeable structural lenses:

- **6** capacity-based national camps,
- **5** count-based project ecologies, and
- only partial alignment between the two.

The core finding is simple:

> Project abundance is not the same as system weight.

A country can look like a small-operating ecology by project count while belonging to a large announced or pre-construction camp by capacity, because a few very large projects control most of the megawatts.

## Count-Capacity Correspondence

![Cross-view correspondence between count ecologies and capacity camps](/images/solar-count-capacity-correspondence.png)

The cross-view correspondence figure is the most important result visually. It shows that count ecologies and capacity camps overlap, but they do not map one-to-one.

Some operating-heavy country groups align strongly across views. For example, a high-purity small-operating ecology maps substantially into a 1-5 MW operating capacity camp. But other ecologies disperse across several capacity camps, especially where many small projects coexist with a few large announced or pre-construction projects.

That divergence is the point. Count and capacity are both necessary because they answer different infrastructure questions.

## Validation, Not Just Clustering

This project is not only an exploratory clustering exercise. The detected communities were tested against a degree-preserving null model to evaluate whether the structure was stronger than expected from network configuration alone.

The observed modularity was far above the null baseline:

| View | Observed modularity | Null mean | z-score |
| --- | ---: | ---: | ---: |
| Capacity projection | **0.684** | 0.314 | **37.1** |
| Count projection | **0.618** | 0.293 | **33.3** |

Across **40** null replicates, no randomized graph reached the observed modularity in either view.

This matters because the page is not claiming that an algorithm simply drew attractive groups. The validation shows that the country groupings reflect statistically strong structure in the data.

## What Actually Differentiates Countries

The project also audits which size-status modes drive cross-national differentiation. The 16 modes are not equally important. Most of the signal concentrates in a compact structural core:

- operating | 1-5 MW,
- operating | 5-50 MW,
- announced | 50-500 MW,
- pre-construction | 50-500 MW.

Two additional modes are more view-specific:

- pre-construction | 5-50 MW is more count-specific,
- announced | 500+ MW is more capacity-specific.

The takeaway:

> Global solar differentiation is driven by a compact structural core, not by all project categories equally.

That mode-salience audit helps explain why the country groups form, rather than stopping at the fact that they exist.

## What This Project Demonstrates

Although the empirical domain is global solar infrastructure, the analytical capabilities are portable across many data-intensive fields.

This project demonstrates:

- large-scale public infrastructure data cleaning and scope design,
- feature representation for cross-country comparison,
- row normalization and similarity-space construction,
- sparse country-network projection,
- Louvain community detection,
- dual-view analysis of count and capacity data,
- null-model validation and sensitivity analysis,
- feature-interpretation through mode salience auditing, and
- scientific visualization for policy-oriented interpretation.

The same underlying skill set is transferable to healthcare, public data systems, and other domains where the hard part is not only building a model, but defining the analytical unit, constructing comparable profiles, validating structure, and explaining what drives the result.

## Technical Notes

The analysis uses cosine similarity on row-normalized country-mode profiles, then constructs sparse top-k country projections before applying Louvain community detection. Capacity serves as the primary analytical path, while count provides a complementary project-frequency lens.

Robustness checks include degree-preserving null-model comparisons, alternative size-bin specifications, and alternative country-inclusion criteria. The goal is not exact membership invariance under every specification, but continuity in the broader structural differentiation logic.
