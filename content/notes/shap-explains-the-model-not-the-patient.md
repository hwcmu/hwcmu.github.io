---
title: "SHAP Explains the Model, Not the Patient"
date: 2026-06-21
draft: false
description: "A concise clinical AI review note on what SHAP can and cannot tell clinicians, researchers, and reviewers."
url: "/blogs/shap-explains-the-model-not-the-patient/"
series: ["Boundary Notes"]
topic: "Clinical Data & Evaluation"
tags: ["Clinical AI", "Model Interpretation", "SHAP"]
---

In my EKG-utilization study, the outcome was whether an emergency-department visit involved an EKG. SHAP helped inspect the fitted model's predictions. Interpreting those attributions required keeping the recorded action separate from a patient's biological need for the test.

> SHAP explains model behavior. It does not establish disease mechanism, treatment effect, or clinical necessity.

## Start with the EKG Case

The [EKG project](/projects/ekg-utilization-prediction/) combined structured emergency-care variables with patient-reported text. The study used SHAP and permutation feature importance to examine the model alongside its predictive performance.

A feature that contributes to a prediction of EKG use may reflect symptoms, care intensity, or an ordering pattern. Its attribution describes how the fitted model uses that information. It does not demonstrate that changing the feature would change disease risk, or that a particular patient should receive the test.

This is an outcome-definition problem before it is an explainability problem. The [published study](https://doi.org/10.3390/jpm15080358) models observed utilization, so its explanations must stay within that interpretation.

## Read an Attribution on Its Own Scale

SHAP allocates the difference between a model output and a reference value among input features. The reference data, explanation method, and model output scale all matter. Contributions may be expressed on a log-odds scale rather than as percentage-point changes in probability.

For an individual visit, an explanation describes that prediction. A summary across visits describes patterns in the fitted model. Neither automatically estimates a causal effect or a population-level clinical relationship.

## Use Explanations to Find Questions Worth Auditing

Useful checks include whether the model relies on variables recorded after the intended prediction time, source-system identifiers, documentation artifacts, or other proxies for the label.

An unexpected attribution is a reason to inspect the feature's provenance and timing. It is not proof of leakage by itself. Conversely, a clinically plausible plot does not establish that the model is free of leakage or will work elsewhere.

Correlated features require particular care: attribution can be distributed among related inputs in ways that depend on the explanation setup. A neat ranking should not be read as a definitive ranking of biological importance.

For complex survey data, the interpretation also depends on how the model was fit and evaluated. SHAP values for an analytic-sample model do not automatically describe nationally weighted clinical patterns.

## Review the Claim Alongside the Plot

Before accepting an interpretation, ask:

- What output and reference population are being explained?
- Are local explanations distinguished from global summaries?
- Could prominent features reflect timing errors, workflow proxies, or correlated measurements?
- Does the wording stay within prediction, or claim an intervention effect?
- What evidence supports calibration and performance in the intended setting?

Feature attribution complements validation. The [transportability note](/blogs/predictive-performance-does-not-establish-transportability/) explains why an interpretable model still needs evaluation across the boundary where it will be used.

## Sources

- Wang H, Zhang X. [Machine Learning for Personalized Prediction of Electrocardiogram (EKG) Use in Emergency Care](https://doi.org/10.3390/jpm15080358). *Journal of Personalized Medicine*. 2025.
- Lundberg SM, Lee SI. [A Unified Approach to Interpreting Model Predictions](https://arxiv.org/abs/1705.07874). NeurIPS 2017.
- SHAP documentation. [An introduction to explainable AI with Shapley values](https://shap.readthedocs.io/en/latest/example_notebooks/overviews/An%20introduction%20to%20explainable%20AI%20with%20Shapley%20values.html).
