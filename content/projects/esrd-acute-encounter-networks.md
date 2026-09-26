---
title: "Mapping Acute ESRD Care: From Presenting Reasons to Diagnostic Networks"
date: 2026-07-23
draft: false
description: "A multi-scale clinical network analysis connecting presenting reasons, ICD-10 chapters, and diagnosis-code pathways across ESRD-indicated emergency encounters."
tags: ["Clinical Network Analysis", "Emergency Care", "Kidney Disease"]
provenanceStatus: "verified"
provenanceSources:
  - "https://doi.org/10.1007/s13721-026-00848-7"
projectType: "Research Project"
role: "Lead author · Cohort design · Network analysis · Robustness assessment"
highlight:
  title: "Trace the encounter from symptom to diagnostic backbone"
  text: "Three linked representations show how broad presenting reasons converge onto a renal-centered diagnostic architecture, connecting information available at presentation with diagnoses recorded after evaluation."
supportingHighlights:
  - title: "One cohort, three clinical scales"
    text: "Chapter-level, diagnosis-code, and symptom-diagnosis layers separate system-wide coupling from specific pathways without collapsing the encounter into a frequency table."
  - title: "The backbone survived alternative definitions"
    text: "Multiple edge weights, an explicit-coding sensitivity analysis, and a pre-pandemic comparison test whether the renal-centered structure depends on one analytical choice."
doi: "10.1007/s13721-026-00848-7"
---

![Diagnosis-code backbone for ESRD-indicated emergency encounters](/images/esrd-diagnosis-code-backbone.jpg)

## Why a Frequency Table Was Not Enough

Emergency encounters among people with end-stage renal disease (ESRD) rarely fit inside one organ system. A patient may arrive with weakness, dyspnea, digestive symptoms, or another broad complaint, while the eventual diagnostic record spans renal, cardiovascular, metabolic, infectious, and dialysis-related concerns.

This project asks a structural question:

> How do presenting reasons and diagnoses organize together within an acute ESRD encounter?

Using the 2020-2022 National Hospital Ambulatory Medical Care Survey emergency-department files, I identified **533 ESRD-indicated encounters** from **47,092 public-use records**. The analysis is deliberately encounter-level and unweighted: its purpose is to map co-occurrence structure within the analytic sample, not estimate national prevalence.

## One Encounter, Three Analytical Scales

The design uses all available presenting-reason fields (`RFV1-RFV5`) and diagnosis fields (`DIAG1-DIAG5`) to construct three complementary views:

1. an **ICD-10 chapter network** for broad system-level coupling;
2. a **Top-50 diagnosis-code network** for specific clinical pathways; and
3. **symptom-diagnosis heatmaps** linking early presenting reasons to downstream diagnoses.

![Cohort definition and three-layer analytical design](/images/esrd-multiscale-study-design.jpg)

Two entities form an edge when they appear in the same encounter. Raw co-occurrence count is the primary weight because it preserves operational volume. Weighted degree, betweenness centrality, density, path length, and Louvain communities summarize the resulting topology. Display thresholds simplify the backbone figures, while all reported network metrics come from the complete, unfiltered graphs.

The chapter network contained **18 nodes and 112 edges**; the code-level network contained **50 nodes and 382 edges**. Moving between these scales makes it possible to see both the overall system architecture and the diagnoses responsible for it.

## What Did the Clinical Map Reveal?

At the chapter level, the Genitourinary System was the dominant hub. Its strongest links were to Symptoms/Signs not elsewhere classified (`n11 = 111`) and the Circulatory System (`n11 = 110`), forming a renal-symptom-cardiovascular backbone.

At the code level, `N18.6` (end-stage renal disease) and `Z99.2` (dialysis dependence) formed the strongest edge (`n11 = 64`). Hypertension, heart failure, hyperkalemia, anemia, diabetes, dyspnea, chest pain, hypoxemia, and weakness extended from this renal-dialysis core.

The cohort definition also exposed a documentation boundary. Although all 533 encounters were identified through the ESRD chronic-condition indicator, only **34.0%** explicitly included `N18.6` among the five available diagnosis fields. A cohort based only on visit diagnosis codes would therefore represent a different clinical population.

## From Broad Symptoms to a Renal Axis

The symptom-diagnosis layer shows a funnel rather than a one-to-one mapping. General, respiratory, and digestive presentations repeatedly converge onto renal-centered diagnoses.

![Symptom-to-diagnosis convergence in ESRD-indicated encounters](/images/esrd-symptom-diagnosis-heatmap.jpg)

The strongest code-level links included General Symptoms to `N18.6` (`n11 = 62`) and Respiratory Symptoms to `N18.6` (`n11 = 55`). This does not mean those symptoms are specific to ESRD. It shows that, within this cohort, nonspecific entry points repeatedly led into renal, dialysis, cardiovascular, and metabolic diagnostic pathways.

## Did the Backbone Depend on One Metric?

Co-occurrence networks can change when edge definitions change. I repeated the analysis using Jaccard similarity, cosine similarity, the phi coefficient, odds ratios, and relative risks.

`N18.6` remained the leading hub under count, Jaccard, cosine, and phi weighting and remained highly ranked under odds-ratio and relative-risk specifications. Association-oriented metrics also surfaced rarer, more specific pairings that raw counts tended to obscure.

Two further checks tested whether the result was driven by explicit `N18.6` coding or by the COVID-era study window. Renal-context structure remained visible when `N18.6` was absent from the diagnosis fields, and the central chapter rankings and `N18.6-Z99.2` edge persisted in a 2018-2019 pre-pandemic comparison.

## What This Map Can Support

The project translates heterogeneous emergency records into an interpretable clinical map that can generate hypotheses for triage pathways, cross-service coordination, and decision-support design.

It does not establish causal direction, patient trajectories, severity, or treatment effects. NHAMCS limits presenting reasons and diagnoses to five fields, lacks longitudinal patient identifiers and dialysis modality, and the unweighted networks are not national estimates. The observed pathways should therefore guide prospective questions, not be treated as validated clinical rules.

Project figures are reproduced from the open-access article under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
