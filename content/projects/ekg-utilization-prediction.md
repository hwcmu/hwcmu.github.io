---
title: "Multimodal Prediction of EKG Use in Emergency Care"
date: 2025-08-06
draft: false
description: "Combined structured ED data with Clinical-BERT narrative features to predict observed EKG use, reaching AUC 0.861 with logistic regression."
topic: "Health & Clinical Decision Systems"
tags: ["Clinical AI", "NLP", "Healthcare Utilization"]
projectType: "Published Research Project"
role: "Lead author · Study design · Clinical NLP · Multimodal modeling"
highlight:
  title: "The modalities are more useful together"
  text: "For logistic regression, combining structured emergency-care variables with Clinical-BERT narrative features raised AUC from 0.772 and 0.823 in the separate inputs to 0.861 in the multimodal model."
supportingHighlights:
  - title: "A linear model stayed competitive"
    text: "Logistic regression slightly outperformed the combined support vector machine, showing that multimodal value did not depend on the most complex classifier."
  - title: "Utilization is not clinical need"
    text: "The model studies observed EKG use and cannot determine whether an individual patient biologically needed the test."
doi: "10.3390/jpm15080358"
codeUrl: "https://github.com/hwcmu/EKG-prediction"
---

![ROC comparison across structured, narrative, and combined EKG-utilization models](/images/ekg-multimodal-roc.jpg)

## Define the Outcome Before Explaining the Model

I developed a multimodal prediction workflow for **observed EKG use** in emergency care. An EKG-use label reflects symptoms and measured physiology, but also clinician judgment, triage practice, and the circumstances of a visit. Predicting that label does not establish whether a test is medically necessary.

The study used **13,115 adult visits** from the 2021 NHAMCS-ED survey. EKG use was recorded in **30.6%** of visits. This is an encounter-level survey, rather than a longitudinal hospital EHR with patient trajectories.

## Compare the Modalities Before Combining Them

The structured inputs included demographics, vital signs, comorbidities, arrival mode, insurance, and triage acuity. Lasso selected a parsimonious structured feature set; Clinical-BERT represented the short chief-complaint and reason-for-visit narratives.

I compared logistic regression, support vector machines, random forests, and XGBoost across structured-only, narrative-only, and late-fusion combined configurations. This makes the incremental contribution of each modality inspectable instead of reporting only a final multimodal score.

## A Linear Model Remained Competitive

For logistic regression, AUC increased from **0.772 with structured inputs** and **0.823 with narrative features** to **0.861 with the combined model**. The combined support vector machine reached **0.860**.

The result supports complementary information in the two inputs. It also shows why classifier complexity and representation quality should be evaluated separately: a linear classifier remained competitive once the modalities were combined.

SHAP and permutation feature importance were used to inspect predictive behavior. An attribution to a symptom or demographic variable describes the fitted model's prediction of EKG use; it does not identify a biological cause of cardiac disease. The companion [SHAP note](/blogs/shap-explains-the-model-not-the-patient/) develops that distinction using this project.

## What Would Need Testing Before Deployment?

These results support retrospective modeling of utilization. They do not validate a live triage queue, a pre-order prompt, or a rule for withholding an EKG.

Before such a use, the prediction time and feature availability would need explicit verification in the target workflow. Calibration, false negatives, subgroup performance, and external or prospective validation would also need evaluation. NHAMCS visits cannot be linked to unique patients, and survey-based associations should not be treated as patient-level causal effects.

The reproducible contribution is the comparison: define the target, evaluate modalities separately and together, and interpret the model at the level its labels can support.
