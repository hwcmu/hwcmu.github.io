---
title: "Multimodal Prediction of IV Fluid Utilization"
date: 2025-12-09
description: "Benchmarked three text representations alongside structured data from 13,115 ED visits; CountVectorizer with gradient boosting reached AUC 0.786."
topic: "Health & Clinical Decision Systems"
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

## Does More Complex NLP Add More Useful Signal?

I compared structured emergency-care variables with short patient narratives to examine whether text improves prediction of IV fluid use. The study analyzed **13,115 adult visits** from the 2021 National Hospital Ambulatory Medical Care Survey emergency-department dataset (NHAMCS-ED).

The practical question was representation choice. Brief reason-for-visit fields contain symptom terms and shorthand; an embedding model can add computational complexity without preserving more useful information for this task.

## Keep the Representation Comparison Visible

I separated text preprocessing from the downstream classifier so that the analysis could compare each representation within a common workflow:

1. Clean and encode structured demographic, visit, and clinical variables.
2. Represent patient narratives using **CountVectorizer, Word2Vec, or pretrained GPT-2 embeddings**.
3. Concatenate structured and text features through early fusion.
4. Compare logistic regression and gradient boosting, using **five-fold cross-validation** and AUC as the primary metric.

The public repository includes the text-processing, data-preparation, and model-comparison workflow. These are retrospective evaluation results; cross-validation does not demonstrate performance in another hospital.

## Match Model Complexity to the Text

The integrated CountVectorizer configuration reached **AUC 0.786 with gradient boosting** and **0.781 with logistic regression**. The integrated GPT-2 gradient boosting configuration reached **0.772**. Combined inputs performed better than either modality alone in the reported comparisons.

For this dataset, the simpler representation captured useful signal from short, keyword-driven narratives. That supports testing an inexpensive baseline before selecting a larger language model. It does not establish that frequency-based features will outperform embeddings for longer notes, other outcomes, or other settings.

## Keep Utilization Separate from Treatment Need

The label records whether IV fluids were used during a visit. It reflects clinical decisions and practice patterns as well as patient state. The model therefore describes observed utilization; it does not determine who needs treatment.

The reported discrimination is insufficient to establish probability calibration, benefit at a treatment threshold, or readiness for automated ordering. External validation and a clearly specified use case would be needed before considering a local clinical application.

The [transportability note](/blogs/predictive-performance-does-not-establish-transportability/) explains why validation must cross the same boundary as the intended use. Here, the contribution is a reproducible comparison of modalities and text representations, with that boundary kept explicit.
