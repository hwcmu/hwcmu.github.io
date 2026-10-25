---
title: "Test Clinical Models Across Disruptive Periods"
date: 2026-07-03
draft: false
description: "A method note on matching validation and training periods to the setting where a clinical model will be used."
url: "/blogs/temporal-validation-disruptive-periods/"
aliases: ["/blogs/train-in-peacetime-test-in-wartime/"]
series: ["Boundary Notes", "Research Workflow Notes"]
tags: ["Temporal Validation", "Data Leakage", "Model Evaluation"]
---

> Random splitting can support internal validation in a defined source population. When the intended use is in a later period, a separate temporal assessment can test whether performance changes over time.
>
> This note covers the prediction time, evaluation period, and changes in clinical practice that can affect a model's use.

<aside class="sticky-glossary">
  <details open>
    <summary>Quick glossary</summary>
    <dl>
      <dt>Look-ahead bias / time travel</dt>
      <dd>Training used future information the model could not have known at prediction time.</dd>
      <dt>Temporal validation</dt>
      <dd>Split strictly by chronological order: train on the past, predict the future.</dd>
      <dt>Walk-forward / rolling-origin</dt>
      <dd>Slide the training window forward; each step predicts only the segment right after it.</dd>
      <dt>Dataset shift</dt>
      <dd>Train- and deployment-time distributions differ.</dd>
      <dt>Covariate shift</dt>
      <dd>The distribution of the input X changes.</dd>
      <dt>Prior-probability shift</dt>
      <dd>The baseline rate of the outcome Y changes.</dd>
      <dt>Concept shift</dt>
      <dd>The relationship between X and Y itself changes.</dd>
      <dt>Discrimination (AUC)</dt>
      <dd>Whether high- and low-risk cases are ranked in the right order.</dd>
      <dt>Calibration</dt>
      <dd>Whether predicted probability values are accurate.</dd>
      <dt>Recalibration</dt>
      <dd>Adjust the overall risk level to realign an aging model with reality.</dd>
      <dt>TRIPOD / TRIPOD+AI</dt>
      <dd>Clinical prediction reporting standards that recommend external temporal or geographic validation.</dd>
    </dl>
  </details>
</aside>

---

## 1. Random Split and Temporal Split Are Not Measuring the Same Thing

There are two common ways to split. A **random split** pools every year's data together, shuffles it, and randomly divides it into train and test. A **temporal split** respects chronological order: train on the past, predict the future.

They are not testing the same ability:

| | Random split | Temporal split |
| --- | --- | --- |
| Main question | How does the model perform in a sample drawn from the development setting? | How does a fixed model perform in a later period? |
| Useful for | Internal validation when the target population matches the source | Checking performance across a time boundary relevant to use |
| Limitation | Does not by itself establish future performance | One later period does not establish performance in every future setting |

The choice depends on the claim. A temporal split is useful when future use is the question, but it does not replace sound internal validation or make a model "understand" a clinical process.

---

## 2. The Most Common Traps When Time Is a Variable

**Trap 1: A mixed-period split may miss temporal change.** If the intended use is later deployment, training and testing on a random mix of years can hide performance drift.

**Trap 2: Independent samples do not make eras independent.** Even if patients or visits never repeat, the system around them changes; what leaks is the future environment.

**Trap 3: Future information enters preprocessing.** Scaling, imputation, encoding, and summaries must be learned from training data only: every value must depend only on information available at prediction time.

**Trap 4: Watching discrimination but ignoring calibration.** AUC may stay stable while predicted probabilities drift. The model can still rank cases correctly while the absolute risks become unusable. **Under temporal drift, you have to watch both.**

---

## 3. How to Do Temporal Validation Properly

**Match the split to the intended use.** For later deployment, evaluate a fixed model on observations collected after its training period. Keep a separate internal validation strategy for model development.

**Use walk-forward evaluation when one cutoff is too fragile.** Keep sliding the training window forward and predict only the segment immediately after it. This can show how performance changes across several time boundaries.

**Validate across the boundary being claimed.** A later period at the same site tests a time boundary; a different site tests a setting boundary. Internal cross-validation alone cannot answer those questions.

---

## 4. How to Handle a Special Period Like the Pandemic

COVID was a **regime shift**: bed availability, staffing, discharge thresholds, and access to community care changed together. Inputs, baseline outcome rates, and feature-outcome relationships all shifted.

Whether to train on a disruptive period depends on the intended use. If the model is meant for ordinary operations, a disruptive period can be a valuable stress test. If the model must operate during a disruption, excluding that period from training may make the development data less relevant.

For either aim, keep evaluation periods separate from training, describe what changed in care delivery, and measure discrimination and calibration in each period. Performance in one disrupted period does not prove that a model has learned a stable mechanism.

So keep this distinction in mind:

> **A disruptive period can test transport across time or supply relevant training data. Its role follows from the target setting and a prespecified evaluation plan.**

When drift appears, diagnose the change before deciding between recalibration, updating, or rebuilding. A temporal assessment makes drift visible, but the appropriate response depends on what shifted and where the model will be used.

---

*The takeaway: choose training and validation periods for the intended use, keep future outcomes out of model development, and report performance where the model is meant to operate.*

## Source

- Riley RD, et al. [Evaluation of clinical prediction models (part 1): from development to external validation](https://www.bmj.com/content/384/bmj-2023-074819). *BMJ*. 2024.
