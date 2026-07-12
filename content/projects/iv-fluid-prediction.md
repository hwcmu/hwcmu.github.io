---
title: "Multimodal Prediction of IV Fluid Utilization"
date: 2025-12-09
description: "A multimodal clinical prediction project combining structured emergency-department variables with reason-for-visit text to study IV fluid utilization."
tags: ["NLP", "Machine Learning", "Healthcare"]
projectType: "Research Project"
role: "Lead author · Data analysis · Multimodal modeling"
highlight:
  title: "The simpler text model won"
  text: "CountVectorizer outperformed GPT-2 embeddings for short emergency-department narratives, showing that representation should follow the structure of the text rather than model fashion."
supportingHighlights:
  - title: "Two data types, one fair comparison"
    text: "Structured visit variables and reason-for-visit text are processed separately, then combined under the same modeling and evaluation framework."
  - title: "Utilization is not clinical necessity"
    text: "The page keeps the outcome boundary visible: the model studies observed IV fluid use and does not recommend treatment."
doi: "10.7717/peerj-cs.3441"
codeUrl: "https://github.com/hwcmu/IVF-prediction"
---

![Multimodal architecture for IV fluid utilization prediction](/images/iv-fluid-architecture.svg)

## A Simple Question with Two Kinds of Data

Emergency-department datasets contain both structured variables and short reason-for-visit narratives. This project tests whether those brief text fields add useful predictive information for IV fluid utilization, and whether more complex language representations are necessarily better for this task.

## Bringing Numbers and Visit Text Together

The analysis uses **13,115** adult visits from the National Hospital Ambulatory Medical Care Survey emergency-department data. Inputs include demographics, visit characteristics, clinical variables, and short patient-reason text.

The workflow keeps the two modalities separate until modeling:

1. structured variables are cleaned and encoded,
2. visit narratives are represented with CountVectorizer, Word2Vec, or pretrained GPT-2 embeddings,
3. structured and text features are combined through early fusion, and
4. logistic regression and gradient boosting models are compared under the same evaluation framework.

This design makes the contribution of each text representation visible rather than treating the multimodal model as a single opaque system.

## When Simpler Language Features Win

The highest-performing integrated gradient boosting configuration reached an **AUC of 0.786**. The CountVectorizer representation outperformed the GPT-2 embedding configuration, which reached **0.772**.

That result is useful because the narratives are short, telegraphic, and often organized around direct symptom terms. In this setting, word frequency can preserve the signal the model needs without introducing the additional complexity of a contextual embedding.

The finding is not that simple NLP is always superior. It is that representation choice should follow the structure of the text and the decision being modeled.

## What the Result Does and Does Not Mean

Adding reason-for-visit text improved the model's ability to study utilization beyond structured variables alone. It also showed that a comparative pipeline can be more informative than selecting a language model in advance.

This remains a retrospective analysis of a public survey dataset. The outcome describes observed IV fluid utilization, not whether treatment was clinically necessary. The model is not a treatment recommendation system, and its performance should not be assumed to transfer to a specific hospital without external validation.

## Why This Comparison Matters

The project brings cohort preparation, mixed-data preprocessing, NLP comparison, model evaluation, and interpretation into one reproducible workflow. Its central lesson is methodological: multimodal clinical modeling works best when each data source is tested for what it actually contributes, with the outcome and intended claim kept visible.
