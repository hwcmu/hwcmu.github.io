---
title: "Real-Time Flight Delay Prediction"
date: 2025-12-13
description: "Connected 4M+ historical flight records, live NOAA temperatures, and TabPy scoring to a Tableau interface with explanations for predicted delays."
topic: "Applied ML & Data Products"
tags: ["Tableau", "Python", "Machine Learning"]
projectType: "Technical Project"
role: "Data pipeline · Modeling · Dashboard integration"
highlight:
  title: "A live model that reaches the dashboard"
  text: "The strongest part is the full connection from historical flight data and current NOAA weather to Python inference inside an interactive Tableau workflow."
supportingHighlights:
  - title: "Weather arrives at prediction time"
    text: "Live conditions are assembled with route and timing features instead of relying on a fixed historical snapshot."
  - title: "Predicted delays have inspectable contributors"
    text: "For flights predicted to be delayed, the dashboard surfaces three SHAP contributors to help users inspect the model output."
codeUrl: "https://github.com/hwcmu/Real-Time-Flight-Delay-Prediction-TabPy-Tableau-NOAA-Integration"
posterUrl: "/docs/project-poster.pdf"
---

![Tableau interface for real-time flight delay prediction](/images/airport.png)

## Connect Offline Training to an Interactive Interface

I built a prediction workflow connecting more than **4 million historical flight records**, current NOAA weather observations, Python inference through TabPy, and a Tableau interface. The engineering task was to carry data and feature definitions from offline modeling into an interactive scoring path.

The repository documents a **15-feature logistic regression model** and separate endpoints for probability, class label, and explanation. The dashboard is the interface to the Python workflow rather than a separate implementation of the model.

## Distinguish Live Inputs from Historical Context

1. Historical Bureau of Transportation Statistics records supply route, schedule, and operational features.
2. A historical lookup table supplies rolling statistics and other contextual values.
3. The NOAA API supplies current origin and destination temperatures.
4. Python assembles the hybrid feature vector and applies the trained logistic regression model.
5. TabPy returns results to Tableau; for predicted delays, the explanation endpoint supplies the top three SHAP contributors.

This distinction matters: a live weather request does not make every input live. Several rolling features remain historical lookups. Explanations describe the fitted prediction and should not be presented as established causes of a delay.

## Choose a Model That Fits the Serving Path

Logistic regression provides probability outputs and a comparatively simple inference path. TabPy lets the workbook request scoring and explanation through a shared Python backend, keeping feature processing separate from presentation.

The public materials support this architecture. They do not establish a latency service-level objective, a production concurrency limit, or a quantified accuracy sacrifice relative to a heavier model, so those are not claimed here.

## Understand the Demo Boundary

The complete interactive workflow requires a running TabPy service and the corresponding Tableau connection. Tableau Public does not support that external service; the public image and poster therefore illustrate the interface rather than offering a live hosted prediction endpoint.

As a prototype, the system shows how historical ML features, current external inputs, and a BI interface can be connected. Operational use would require separate evaluation of input freshness, API failure behavior, model drift, and performance under the intended traffic pattern.
