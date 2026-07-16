---
title: "Predicting EKG Utilization from Clinical Variables and Patient Narratives"
date: 2025-08-06
draft: false
description: "A published multimodal clinical AI study combining structured emergency-care variables with patient-reported text to model observed EKG utilization."
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

## What Does an EKG Prediction Model Actually Predict?

An electrocardiogram is central to evaluating chest pain, dyspnea, arrhythmia, and other potentially serious presentations in emergency care. But an EKG is not performed during every visit. Its use reflects a mixture of symptoms, measured physiology, comorbidity, triage severity, clinician judgment, and local workflow.

This project asked whether structured clinical variables and short patient-reported narratives could be combined to predict whether an EKG was performed during an emergency department visit.

The outcome boundary is essential: the model predicts **observed EKG utilization**. It does not determine whether a patient should receive an EKG, and it does not identify biological necessity.

## Two Data Modalities, One Clinical Encounter

The published study analyzed **13,115 adult emergency department visits** from the nationally representative 2021 National Hospital Ambulatory Medical Care Survey-Emergency Department dataset. EKGs were recorded in **30.6%** of visits.

The analysis separated the available information into two modalities:

- structured variables, including demographics, vital signs, comorbidities, arrival mode, insurance, and triage acuity; and
- short narrative fields describing the patient's chief complaint and reason for visit.

Lasso was used to select a parsimonious structured feature set. The narrative fields were represented with Clinical-BERT embeddings. Logistic regression, support vector machines, random forests, and XGBoost were then compared under structured-only, text-only, and late-fusion combined conditions.

This design made the contribution of the narrative visible instead of treating the final model as one opaque multimodal system.

## What Changed When the Modalities Were Combined?

Structured variables alone produced an AUC of approximately **0.772**. Text-only configurations reached approximately **0.822 to 0.823**. The strongest combined models reached **0.861 for logistic regression** and **0.860 for the support vector machine**.

The result is useful for two reasons. First, patient-reported text captured information that was not fully represented by coded fields. Second, a comparatively simple linear model remained competitive after the two modalities were combined.

The study also used SHAP values and permutation feature importance to audit model behavior. Those tools help explain which inputs influenced prediction, but they do not convert utilization predictors into causes of disease or proof of clinical need.

## What the Result Can and Cannot Support

The study shows that structured emergency-care variables and short patient narratives contain complementary information about EKG use. It does not show that the model is ready to recommend testing in a live hospital.

Important boundaries remain:

- NHAMCS-ED is a national visit survey, not a longitudinal hospital EHR;
- visits cannot be linked back to unique patients;
- the analysis models observed practice and may reproduce existing workflow patterns;
- discrimination does not establish calibration or benefit at a clinical decision threshold; and
- external validation is required before considering deployment in a specific care setting.

The transferable contribution is the analytical discipline: define the prediction target, preserve the distinction between care behavior and clinical need, compare each modality fairly, and interpret the model at the level the data can support.
