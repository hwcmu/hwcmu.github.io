---
title: "AI-Powered Migraine Forecast System"
date: 2025-12-06
description: "Connected SQL product metrics, physician-guided random-forest forecasting, and longitudinal feedback in a migraine-management product."
topic: "Applied ML & Data Products"
tags: ["Product Analytics", "Machine Learning", "Healthcare"]
projectType: "Product Analytics Project"
role: "Data scientist · Product analytics · Forecasting"
highlight:
  title: "Connect forecasting to a product people can use"
  text: "The work combined product metrics, physician-guided feature selection, and risk-output smoothing, with public claims limited to the documented design."
supportingHighlights:
  - title: "Metrics come before modeling"
    text: "A shared product analytics framework made adoption, onboarding, and retention visible before new predictive features were evaluated."
  - title: "Feedback gives users value now"
    text: "Personalized longitudinal summaries turned user logs into readable feedback that people could revisit."
productUrl: "https://www.peachyday.co/"
codeStatus: "private"
---

![Migraine forecast interface and risk trajectory](/images/migraine-forecast.png)

## Build the Measurement Layer Before the Forecast

At [PeachyDay](https://www.peachyday.co/), my work connected product analytics, physician-guided forecasting, and personalized feedback for people recording migraine-related information. The practical problem extended beyond a classifier: the team needed consistent metrics, interpretable inputs, and a useful way to return information to users.

I developed SQL definitions for active use, feature adoption, onboarding progression, and retention. Dashboards made user flows and drop-off points visible, providing a shared basis for discussing product changes.

## Translate Clinical Input into a Forecasting Workflow

The forecasting pipeline combined user history, health observations, activity, and weather context. Clinical input informed feature selection, including the use of barometric-pressure change.

![PeachyDay system architecture with physician-in-the-loop](/images/migraine-architecture.png)

The workflow used a random forest with post-processing intended to reduce abrupt risk changes and unnecessary alerts. This was a design choice about the behavior of a recurring user-facing signal. Smoothing should not be confused with demonstrated probability calibration.

User-entered records also raise evaluation questions: when observations are missing, what is known at prediction time, and whether logging behavior changes with symptoms. Those questions matter when interpreting any retrospective performance estimate.

## Return Value Beyond a Risk Score

I also developed personalized longitudinal summaries that let users revisit patterns in the information they had recorded. This created a feedback layer alongside the forecast and connected analytical work to ongoing product use.

The three components served different purposes: product metrics described engagement, forecasting produced a near-term risk signal, and summaries made logged history easier to review. Each needed its own outcome definition rather than a single score standing in for product success.

## Keep the Public Evidence Boundary Clear

The code and internal evaluation details are proprietary. This page describes the design and my contribution; it does not report externally verified gains in accuracy, calibration, retention, or clinical outcomes.

The forecast is a product-support feature for awareness and planning. It is not a diagnosis, a medication recommendation, or a substitute for clinical care.
