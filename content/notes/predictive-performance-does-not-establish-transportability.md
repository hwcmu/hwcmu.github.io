---
title: "Predictive Performance Does Not Establish Transportability"
date: 2026-10-24
draft: false
contentType: "reading-note"
sourceBook: "Scale"
sourceBookZh: "规模"
description: "A clinical AI review framework for testing whether a model can cross hospitals, devices, populations, workflows, and time periods."
url: "/blogs/predictive-performance-does-not-establish-transportability/"
series: ["Boundary Notes"]
tags: ["Model Evaluation", "Dataset Shift", "Transportability"]
provenanceStatus: "verified"
provenanceSources:
  - "https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/"
  - "https://doi.org/10.1214/10-STS330"
  - "https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002683"
  - "https://pmc.ncbi.nlm.nih.gov/articles/PMC8665481/"
  - "https://pmc.ncbi.nlm.nih.gov/articles/PMC10788734/"
  - "https://proceedings.neurips.cc/paper_files/paper/2017/hash/8a20a8621978632d76c43dfd28b67767-Abstract.html"
---

A model that performs well on held-out data has passed an important test. It has not passed every test implied by the word "generalizable."

Internal validation estimates performance under a particular sampling and data-generating process. Transportability asks a stronger question: will the relationship remain useful after the population, institution, workflow, device, time period, or decision context changes?

> Predictive performance is evidence about a model in an evaluated environment. Transportability is a claim about environments that were not interchangeable by default.

## Four Claims That Need Different Evidence

| Claim | Minimum supporting evidence | What it still does not prove |
| --- | --- | --- |
| The model separates higher- and lower-risk cases | Discrimination on an untouched test set | Calibration, clinical utility, external performance |
| The probabilities are usable in this setting | Calibration and decision analysis in the target setting | Stability over time or across sites |
| The model travels to another setting | External or prospective validation under the new process | Causal mechanism or future stability |
| A feature helps explain the outcome | Design and evidence appropriate to an explanatory or causal claim | That the predictive model estimated that mechanism |

Moving down the table strengthens the claim. It also changes the required study design. A random train-test split cannot substitute for external validation merely because its sample size is large.

## The Source Environment Can Become a Predictor

In a multicenter pneumonia-detection study, Zech and colleagues found variable performance when chest-radiograph models moved across hospital systems. The models could also distinguish image source with very high accuracy.

Hospital identity can enter an image through acquisition equipment, processing, patient mix, portable imaging patterns, annotations, and local workflow. If those signals correlate with the label during development, optimization has no reason to ignore them.

This creates a shortcut that may be stable inside one pipeline and unstable elsewhere. The model can be genuinely predictive without having learned a representation that transports.

The same pattern appears in structured clinical data. Ordering frequency, missingness, billing codes, timestamps, and care intensity may reflect local practice as much as patient state. Before deployment, each high-value predictor needs a provenance question: *what process made this variable available?*

Feature attribution can help surface site markers and workflow proxies, but it is an audit tool rather than evidence of transportability. As discussed in [SHAP Explains the Model, Not the Patient](/blogs/shap-explains-the-model-not-the-patient/), explaining what a model used does not establish that the relationship will survive a change of setting.

## Name the Boundary the Model Must Cross

"External validation" is too vague unless the intended move is specified. A new hospital, device, population, time period, and clinical workflow can each change a different part of the data-generating process. The validation design should cross the same boundary that deployment will cross.

| Intended use | More informative validation design |
| --- | --- |
| Future patients in the same system | Temporal holdout with workflow-aware monitoring |
| Another hospital | Site-level external validation |
| A new device or acquisition protocol | Device- or protocol-separated validation |
| A different population | Prespecified subgroup and population validation |
| A live clinical workflow | Prospective evaluation with calibration and operational outcomes |

For the time boundary specifically, [Test Clinical Models Across Disruptive Periods](/blogs/temporal-validation-disruptive-periods/) covers temporal assessments, preprocessing leakage, calibration drift, and changes in the target setting. Here the broader rule is what matters: do not ask one validation design to support a boundary it never crossed.

## Diagnose the Shift Before Repairing the Model

When performance changes, "retrain it" is not yet a diagnosis. Separate at least four possibilities:

1. **Population shift:** patient characteristics or disease prevalence changed.
2. **Measurement shift:** devices, coding, extraction, or missingness changed.
3. **Workflow shift:** clinical behavior changed the relationship between predictors and labels.
4. **Outcome shift:** the target definition, intervention pathway, or event rate changed.

Discrimination, calibration, alert volume, and missing-input rates can move differently. Monitoring only AUC may miss an operationally important failure.

## A Transportability Review

Before making a generalization claim, document:

- the development, validation, and target environments;
- the prediction moment and feature-availability rules;
- how labels are created in each environment;
- which features can encode site or workflow identity;
- discrimination and calibration in each target setting;
- subgroup performance where use or harm may differ;
- the monitoring trigger and response after deployment.

The review should end with a bounded statement, not the word "generalizable." For example:

> The model retained discrimination and calibration in a temporally later cohort from the same health system; performance in other institutions has not been established.

That sentence is less dramatic than a universal claim. It is also much more useful.

## Sources

- Geoffrey West. [*Scale*](https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/). Penguin Books.
- Shmueli G. [To Explain or to Predict?](https://doi.org/10.1214/10-STS330). *Statistical Science*. 2010.
- Zech JR, et al. [Variable Generalization Performance of a Deep Learning Model to Detect Pneumonia in Chest Radiographs](https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002683). *PLOS Medicine*. 2018.
- Finlayson SG, et al. [The Clinician and Dataset Shift in Artificial Intelligence](https://pmc.ncbi.nlm.nih.gov/articles/PMC8665481/). *New England Journal of Medicine*. 2021.
- Riley RD, et al. [Evaluation of Clinical Prediction Models (Part 2): How to Undertake an External Validation Study](https://pmc.ncbi.nlm.nih.gov/articles/PMC10788734/). *BMJ*. 2024.
- Lundberg SM, Lee SI. [A Unified Approach to Interpreting Model Predictions](https://proceedings.neurips.cc/paper_files/paper/2017/hash/8a20a8621978632d76c43dfd28b67767-Abstract.html). NeurIPS 2017.
