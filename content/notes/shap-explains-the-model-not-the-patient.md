---
title: "SHAP Explains the Model, Not the Patient"
date: 2026-06-21
draft: false
description: "A concise clinical AI review note on what SHAP can and cannot tell clinicians, researchers, and reviewers."
url: "/blogs/shap-explains-the-model-not-the-patient/"
series: ["Boundary Notes"]
tags: ["Clinical AI", "Model Interpretation", "SHAP"]
---

In clinical AI papers, SHAP plots are sometimes treated as explanations of disease itself. They are not. SHAP shows what a trained model relied on for a prediction:

> SHAP explains model behavior. It does not prove disease mechanism, treatment effect, or real-world causality.

## 1. What SHAP Actually Explains

SHAP stands for **SHapley Additive exPlanations**. A plain-language version is:

> SHAP divides a model's prediction into contributions from each input feature.

Suppose a model predicts high risk of hospital admission. SHAP asks:

> Which features pushed this model prediction upward or downward compared with a baseline?

| Feature | SHAP-style contribution | Plain meaning |
|---|---:|---|
| High blood pressure | +0.18 | Pushed the model prediction upward |
| Older age | +0.12 | Pushed the model prediction upward |
| Current smoker | +0.08 | Pushed the model prediction upward |
| Normal oxygen saturation | -0.05 | Pulled the model prediction downward |

The scale depends on the model. In some implementations, values are on an internal scale such as log-odds, not percentage-point risk changes.

The safe interpretation is simple:

> SHAP explains the prediction relative to a baseline. It does not automatically explain the patient's biology.

---

## 2. Model Dependence Is Not Causality

SHAP can answer why a model predicted high risk and which variables it relied on. It cannot establish whether a variable causes an outcome or whether intervening on it would change risk.

For example, a model may use cardiology follow-up visits to predict one-year cardiac risk. More visits can mark underlying illness severity, so the careful interpretation is:

> "The model is using follow-up frequency as a marker of underlying illness severity."

not “cardiology visits cause heart disease.” Confusing a severity marker with a cause turns a model explanation into a false treatment target.

---

## 3. When SHAP Is Useful

SHAP is helpful when used for the right question.

For an individual prediction, SHAP can show whether a model relied on age, vital signs, laboratory results, symptoms, or text-derived features. It can also audit shortcuts: hospital ID, timestamps, data-entry artifacts, or variables recorded after the prediction point should prompt investigation.

It is also useful for communicating model behavior. Better:

> "The model assigned higher predicted risk partly because this patient had high blood pressure and abnormal labs."

Too strong:

> "High blood pressure caused this outcome because SHAP ranked it highly."

---

## 4. Common Misuses and Limits

Most problems come from overinterpretation. SHAP cannot tell us whether lowering blood pressure, changing medication, or ordering a test would change an outcome; that needs clinical evidence and an appropriate causal design. A high-SHAP variable may be non-modifiable, a severity marker, a proxy, or a consequence of disease. Before acting, ask:

> Is this feature modifiable, causal, and supported by evidence?

**Over-reading correlated features**

Clinical variables are often correlated. SHAP may split credit across related features in ways that look precise but are not clinically definitive.

**Ignoring survey weights and complex sampling**

For nationally representative or complex survey data, SHAP explains the fitted analytic-sample model; it does not automatically describe nationally weighted clinical patterns.

Reviewer question:

> Are SHAP values being interpreted as model explanations for the analytic sample, or as population-level clinical conclusions?

**Using SHAP instead of validation**

A convincing SHAP plot does not establish reliability. A clinical AI paper still needs a clear outcome, leakage control, discrimination and calibration assessment, appropriate validation, and a plausible use case. SHAP can audit what a model learned; it cannot rescue a poorly designed study.

---

## 5. A Small Case: EKG Use Prediction

My EKG-use prediction work illustrates the boundary. The model predicted whether an emergency-department visit involved EKG use; its interpretation analyses included feature selection, SHAP values, and permutation feature importance. The published article is available at [DOI: 10.3390/jpm15080358](https://doi.org/10.3390/jpm15080358).

SHAP explained which structured and text-derived features contributed to a prediction of EKG utilization; it did not show that these features biologically caused a need for EKG. This matters because EKG use is partly a clinical decision and workflow behavior, not only a disease state.

---

## 6. Reviewer Checklist

Before accepting a SHAP interpretation in a clinical AI paper, ask:

- What exact model output is being explained, and is the language limited to prediction rather than causality?
- Could the leading features be leakage variables, proxies, or non-modifiable severity markers?
- Are global and local explanations separated, and is the interpretation target clear for survey data?
- Has the model been validated and calibrated?

If these questions are unclear, the figure is decorative rather than informative. Let SHAP answer “How did the model think?”; let clinical evidence, validation, and causal reasoning answer “What should we do?”

---

## Sources

- Lundberg, S. M., & Lee, S.-I. *A Unified Approach to Interpreting Model Predictions*. NeurIPS 2017 / arXiv. https://arxiv.org/abs/1705.07874
- SHAP documentation: *An introduction to explainable AI with Shapley values*. https://shap.readthedocs.io/en/latest/example_notebooks/overviews/An%20introduction%20to%20explainable%20AI%20with%20Shapley%20values.html
- TRIPOD+AI statement: updated guidance for reporting clinical prediction models that use regression or machine-learning methods. *BMJ*, 2024. https://www.bmj.com/content/385/bmj-2023-078378
- PROBAST-AI: risk-of-bias and applicability assessment for prediction model studies using artificial intelligence. *BMJ*, 2024. https://www.bmj.com/content/385/bmj-2023-078370
- CONSORT-AI extension: reporting guidelines for clinical trial reports of interventions involving artificial intelligence. *Nature Medicine*, 2020. https://www.nature.com/articles/s41591-020-1034-x
