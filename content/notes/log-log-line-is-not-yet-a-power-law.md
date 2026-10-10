---
title: "A Straight Line on a Log-Log Plot Is Not Yet a Power Law"
date: 2026-10-10
draft: false
contentType: "reading-note"
sourceBook: "Scale"
sourceBookZh: "规模"
description: "A practical guide to reading scaling exponents without confusing a useful visual pattern with a validated power-law model."
url: "/blogs/log-log-line-is-not-yet-a-power-law/"
series: ["Modeling Decisions"]
tags: ["Power Laws", "Statistical Modeling", "Model Diagnostics"]
provenanceStatus: "verified"
provenanceSources:
  - "https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/"
  - "https://doi.org/10.1137/070710111"
  - "https://arxiv.org/abs/0706.1062"
  - "https://www.itl.nist.gov/div898/handbook/mpc/section3/mpc361.htm"
  - "https://doi.org/10.1080/01621459.1983.10478017"
---

A log-log plot can turn a cloud of measurements into a striking straight line. That visual is often the beginning of a scaling analysis. It should not be the end.

If

$$
Y = Y_0 X^b,
$$

then taking logarithms gives

$$
\log Y = \log Y_0 + b \log X.
$$

The exponent $b$ becomes the slope. When $Y$ is a total quantity and $X$ is system size, comparing $b$ with 1 can be informative: $b<1$ suggests sublinear scaling, $b=1$ proportional scaling, and $b>1$ superlinear scaling.

But several different questions are routinely collapsed into that one picture.

## A Scaling Relationship Is Not a Power-Law Distribution

The statement

$$
E[Y\mid X=x] \propto x^b
$$

describes how one variable changes with another. A power-law distribution instead describes the frequency of values in the tail of one variable, often written as

$$
p(x) \propto x^{-\alpha}, \qquad x \geq x_{min}.
$$

These are different models with different estimands. A city outcome may scale with population even when city population itself does not follow a convincing power-law distribution over the full range. Seeing a straight line in one setting does not establish the other.

## Why the Plot Can Mislead

Several processes can look approximately linear after log transformation over a limited range:

- lognormal and stretched-exponential behavior;
- mixtures of distinct subpopulations;
- a curved relationship observed over too narrow a range;
- a few influential observations at the largest scales;
- measurement thresholds that remove small values.

Ordinary least squares on logged data also changes the error model. A model with additive error on the original scale is not equivalent to one with additive error after logging. [NIST's calibration guidance](https://www.itl.nist.gov/div898/handbook/mpc/section3/mpc361.htm) makes the transformed multiplicative-error structure explicit. Back-transforming predictions introduces another issue because the mean of an exponentiated random variable is not simply the exponentiated mean; [Duan's smearing estimator](https://doi.org/10.1080/01621459.1983.10478017) addresses estimation of the expected response on the original scale.

The log-log graph remains useful. It reveals orders of magnitude, heteroscedasticity, possible curvature, and candidate regimes. Its job is diagnosis, not certification.

## A Better Reading Workflow

### 1. Name the claim

Are you modeling a conditional mean, a median, a quantile, or a distributional tail? What does $b$ mean for this particular outcome? The language of "sublinear" and "superlinear" is useful only after the numerator, denominator, and unit of analysis are clear.

### 2. Plot more than one view

Inspect the original scale, log-log scale, and residuals. Add uncertainty and show the density of observations. A line spanning sparse extremes can look more certain than it is.

### 3. Check for regimes and heterogeneity

Fit the same relationship within defensible groups. Species, countries, time periods, device types, and organizational classes may follow different slopes. Pooling them can manufacture a clean average that describes none of them well.

### 4. Compare plausible alternatives

For tail distributions, Clauset, Shalizi, and Newman recommend estimating the lower cutoff and exponent, assessing goodness of fit, and comparing the power law with alternatives rather than relying on a regression line. For scaling regressions, compare nonlinear forms, splines, segmented models, and domain-motivated alternatives.

### 5. Test what the exponent is supposed to predict

If a mechanism implies $b=3/4$, report uncertainty around the estimate and test related implications. If the exponent changes sharply under a reasonable inclusion rule, it is not yet a stable system property.

## The Boundary

Geoffrey West's *Scale* is compelling because an exponent can compress a large system into one interpretable parameter. The danger is turning that compression into premature certainty.

> A log-log line is evidence of a candidate scaling relationship. It is not, by itself, evidence of a universal law.

The exponent becomes useful when the estimand is clear, alternatives have been considered, heterogeneity is visible, and a mechanism explains why the relationship should persist beyond the observed sample.

## Sources

- Geoffrey West. [*Scale*](https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/). Penguin Books.
- Clauset A, Shalizi CR, Newman MEJ. [Power-Law Distributions in Empirical Data](https://doi.org/10.1137/070710111). *SIAM Review*. 2009. [Open manuscript](https://arxiv.org/abs/0706.1062).
- NIST/SEMATECH. [Models for Instrument Calibration](https://www.itl.nist.gov/div898/handbook/mpc/section3/mpc361.htm). *e-Handbook of Statistical Methods*.
- Duan N. [Smearing Estimate: A Nonparametric Retransformation Method](https://doi.org/10.1080/01621459.1983.10478017). *Journal of the American Statistical Association*. 1983.
