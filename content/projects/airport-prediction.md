---
title: "Real-Time Flight Delay Prediction"
date: 2025-12-13
description: "An end-to-end prediction system connecting historical flight records, live NOAA weather, Python inference, and a Tableau decision interface."
tags: ["Tableau", "Python", "Machine Learning"]
projectType: "Technical Project"
role: "Data pipeline · Modeling · Dashboard integration"
highlight:
  title: "A live model that reaches the dashboard"
  text: "The strongest part is the full connection from historical flight data and current NOAA weather to Python inference inside an interactive Tableau workflow."
supportingHighlights:
  - title: "Weather arrives at prediction time"
    text: "Live conditions are assembled with route and timing features instead of relying on a fixed historical snapshot."
  - title: "Every score comes with a reason"
    text: "SHAP surfaces the three strongest contributors so a delay probability is accompanied by an inspectable explanation."
codeUrl: "https://github.com/hwcmu/Real-Time-Flight-Delay-Prediction-TabPy-Tableau-NOAA-Integration"
posterUrl: "/docs/project-poster.pdf"
---

![Tableau interface for real-time flight delay prediction](/images/airport.png)

## From Flight Records to a Live Decision

Flight delays depend on conditions that change across routes, airports, and time. This project connects a model trained on more than **4 million historical flight records** with live weather inputs, allowing a user to explore delay risk through a Tableau interface.

The main challenge was not only training a classifier. It was building a complete path from historical data and an external API to fast inference, explanation, and a usable front end.

## How the Pieces Connect

The workflow combines Bureau of Transportation Statistics records with NOAA weather data:

1. historical flight records are cleaned and summarized into route and timing features,
2. rolling statistics provide recent operational context,
3. the NOAA API supplies current weather conditions,
4. the features are passed to a logistic regression model, and
5. TabPy returns the predicted delay probability to Tableau.

Logistic regression was selected as a practical balance between probability output, inference speed, and interpretability. The project uses SHAP to identify the three features contributing most strongly to each prediction, so the dashboard shows not only a risk estimate but also the conditions influencing it.

## Why the Interface Matters

The dashboard acts as the decision surface rather than the analytical engine. Users select a route and flight context in Tableau; TabPy connects those inputs to the Python model and returns the prediction and explanation.

This separation keeps the components modular:

- Tableau handles interaction and visual communication,
- Python handles feature processing and inference,
- NOAA provides live environmental context, and
- the historical dataset supplies the learned delay patterns.

## What the Public Demo Can Show

Tableau Public does not support an external TabPy service. The public dashboard image and poster therefore show a static demonstration, while the repository documents the complete local architecture and integration workflow.

The project is a prediction prototype rather than an airline operations system. Its outputs depend on the quality and timing of the weather feed, the stability of historical route patterns, and the features available at inference time.

## What Makes the System Useful

The useful part of this project is the connection between modeling and delivery. A model becomes operational only when live inputs are assembled consistently, inference is fast enough for interaction, and the result is communicated in a form that a user can inspect. The project makes that full chain visible from data pipeline to dashboard.
