---
title: "AI-Powered Migraine Forecast System"
date: 2025-12-06
description: "A digital-health analytics project connecting product metrics, physician-guided forecasting, and personalized feedback for migraine management."
tags: ["Product Analytics", "Machine Learning", "Healthcare"]
projectType: "Product Analytics Project"
role: "Data scientist · Product analytics · Forecasting"
highlight:
  title: "Clinical judgment shapes the forecast"
  text: "The forecasting logic was developed with physicians so feature selection and risk smoothing reflect how migraine patterns are understood, not only what improves a model score."
supportingHighlights:
  - title: "Metrics come before modeling"
    text: "A shared product analytics framework made adoption, onboarding, and retention visible before new predictive features were evaluated."
  - title: "Feedback gives users value now"
    text: "Personalized longitudinal summaries returned useful patterns to more than 1,000 users and were associated with a 12% engagement increase."
productUrl: "https://www.peachyday.co/"
codeStatus: "private"
---

![Migraine forecast interface and risk trajectory](/images/migraine-forecast.png)

## Designing for a Recurring Condition

[PeachyDay](https://www.peachyday.co/) is a digital-health product for people managing recurrent migraines. The analytical challenge was broader than building a prediction model: the product needed a consistent way to measure engagement, translate clinical knowledge into features, and return useful feedback to people who logged data over time.

## First, Make Product Behavior Visible

I developed a metrics framework linking product questions to reproducible SQL definitions. It covered active use, feature adoption, onboarding progression, and retention, giving the team a shared basis for evaluating product changes.

The dashboards made user flows and drop-off points visible and helped connect roadmap decisions to observed behavior rather than isolated anecdotes. This analytics layer also provided the monitoring structure needed for later forecasting features.

## Building the Forecast with Clinical Input

The forecasting workflow combines user history, health observations, activity, and weather context. Feature selection was developed with clinical input so that variables such as barometric-pressure change entered the model through an interpretable rationale rather than through unconstrained feature expansion.

![PeachyDay system architecture with physician-in-the-loop](/images/migraine-architecture.png)

The pipeline uses a random forest model with post-processing designed to reduce abrupt risk changes and limit unnecessary alerts. The resulting forecast improved accuracy by **18%** over the project baseline.

Clinical collaboration shaped both the inputs and the behavior of the output. The objective was not to imitate a diagnostic system, but to produce a risk signal that could support reflection and planning without overstating certainty.

## Giving Users Something Back

Prediction alone did not solve the engagement problem. Users needed a reason to keep recording information even when no immediate forecast changed.

I therefore developed a personalized data-story workflow for more than **1,000 users**, summarizing longitudinal patterns in a format inspired by annual listening summaries. This feedback loop was associated with a **12% increase** in user engagement.

## Connecting Prediction and Product Value

The project connects three layers that are often separated:

- product metrics define whether a feature is being used,
- forecasting translates longitudinal data into a near-term signal, and
- personalized summaries return value to the user.

The code is proprietary, so this page documents the analytical design rather than implementation details. The forecast is a product-support feature, not a medical diagnosis or substitute for clinical care.
