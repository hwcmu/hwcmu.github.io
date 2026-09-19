---
title: "A Z-Score Is Not a Dimensionless Feature"
date: 2026-09-19
draft: false
contentType: "reading-note"
sourceBook: "Scale"
sourceBookZh: "规模"
description: "A modeling boundary between sample-relative standardization and dimensionless features designed to preserve behavior across units and scale."
url: "/blogs/z-score-is-not-a-dimensionless-feature/"
series: ["Modeling Decisions"]
tags: ["Dimensional Analysis", "Feature Engineering", "Model Transfer"]
provenanceStatus: "verified"
provenanceSources:
  - "https://doi.org/10.1080/14786442408634474"
  - "https://doi.org/10.1016/0024-3795(82)90229-4"
  - "https://arxiv.org/abs/2202.04643"
  - "https://www.itl.nist.gov/div898/handbook/eda/section3/eda35h.htm"
  - "https://scikit-learn.org/1.6/modules/generated/sklearn.preprocessing.StandardScaler.html"
  - "https://ntrs.nasa.gov/api/citations/19760007927/downloads/19760007927.pdf"
  - "https://pubmed.ncbi.nlm.nih.gov/34431826/"
---

A z-score and a Reynolds number are both unitless. They do not carry the same kind of information.

A z-score says where an observation sits relative to a reference sample. A dimensionless physical group compares variables in a way intended to preserve system behavior when units or scale change.

Confusing the two turns "normalization" into a vague instruction and hides the model built into a feature transformation.

> Standardization removes a sample's location and scale. Dimensional analysis tries to preserve a system's governing relationships.

## Sample-Relative and System-Relative Features

A z-score is defined as

$$
z = \frac{x-\bar{x}}{s}.
$$

It is useful for optimization, regularization, and coefficient comparison. But its meaning depends on the reference mean and standard deviation. Change the population or time period and the same raw value may receive a different score.

A dimensionless group is constructed differently. The squared Froude number, for example, compares inertial and gravitational effects:

$$
Fr^2 = \frac{v^2}{gL}, \qquad Fr = \frac{v}{\sqrt{gL}}.
$$

The units cancel, but cancellation is not the main achievement. The ratio represents a proposed competition between mechanisms. When relevant dimensionless conditions match, differently sized systems may show comparable behavior.

| Transformation | What it preserves | Main dependency |
| --- | --- | --- |
| Unit conversion | Physical quantity | Chosen unit system |
| Z-score | Position in a reference distribution | Reference sample |
| Min-max scaling | Position in a chosen range | Observed extrema |
| Dimensionless group | Relative strength of governing effects | Mechanistic assumptions |

All four can produce convenient numbers. Only the last one claims structural similarity across scale.

## When a Ratio Can Travel

Several common data features have dimensionless or exposure-normalized logic:

- events divided by meaningful time at risk;
- signal compared with noise;
- computation compared with bytes moved;
- concentration expressed as amount per volume;
- a dose related to a defensible body-size measure.

These features may transfer better than raw quantities when the denominator represents a real exposure, constraint, or competing process. The claim is testable: systems with similar values should behave similarly on the outcome the ratio was designed to describe.

This is stronger than saying the feature "helps the model." It says why the feature may remain meaningful after scale changes.

## The Denominator Is a Model

Dividing by a variable silently fixes its exponent at one.

A per-capita outcome $Y/N$ assumes that $Y$ should scale proportionally with population. If the appropriate baseline is instead

$$
Y \propto N^b,
$$

with $b \neq 1$, the ratio leaves systematic size effects behind. The same problem appears when a clinical measurement is divided by body size without checking the appropriate allometric relationship.

Ratios introduce other risks:

- denominators near zero create instability;
- measurement error in the denominator propagates through the feature;
- identical ratios can hide clinically different absolute levels;
- a changing denominator can manufacture an apparent association.

The alternative is not to ban ratios. It is to compare the fixed-ratio assumption with a model that estimates the scaling relationship and preserves the original variables where absolute scale matters.

## A Construction Test

Before adding a ratio or standardized feature, document six decisions:

1. **Purpose:** optimization, comparison, exposure adjustment, or mechanistic similarity?
2. **Reference:** which sample defines the center, spread, or range?
3. **Units:** which dimensions cancel, and why should they cancel?
4. **Mechanism:** what processes does the feature compare?
5. **Boundary:** what happens near zero, at measurement limits, or outside the training range?
6. **Alternative:** does an estimated nonlinear or allometric form fit and transfer better?

For deployment, store the training reference values used for z-scores. Recomputing them silently on a new cohort changes the representation and can conceal population shift.

## What the Transformation Can Claim

A z-score can make an optimization problem easier and place features on comparable numerical scales. It does not, by itself, create a transferable scientific variable.

A meaningful dimensionless group can encode a relationship that survives changes in units and size. It earns that interpretation through domain assumptions and empirical testing, not through the absence of units alone.

The useful question is not "Has this column been normalized?" It is:

> Relative to which sample or mechanism has the column been transformed, and what invariance is the transformation claiming?

## Sources

- Buckingham E. [Dimensional Analysis](https://doi.org/10.1080/14786442408634474). *Philosophical Magazine*. 1924.
- Curtis WD, Logan JD, Parker WA. [Dimensional Analysis and the Pi Theorem](https://doi.org/10.1016/0024-3795(82)90229-4). *Linear Algebra and its Applications*. 1982.
- Bakarji J, Callaham JL, Brunton SL, Kutz JN. [Dimensionally Consistent Learning with Buckingham Pi](https://arxiv.org/abs/2202.04643). 2022.
- National Institute of Standards and Technology. [Z-Scores and Modified Z-Scores](https://www.itl.nist.gov/div898/handbook/eda/section3/eda35h.htm).
- scikit-learn. [StandardScaler documentation](https://scikit-learn.org/1.6/modules/generated/sklearn.preprocessing.StandardScaler.html).
- NASA. [Similarity relations and Froude scaling](https://ntrs.nasa.gov/api/citations/19760007927/downloads/19760007927.pdf).
- [How Should Adult Handgrip Strength Be Normalized? Allometry Reveals New Insights and Associated Reference Curves](https://pubmed.ncbi.nlm.nih.gov/34431826/). *Medicine & Science in Sports & Exercise*. 2021.
