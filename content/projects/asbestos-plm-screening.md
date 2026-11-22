---
title: "Deep Learning-Assisted Chrysotile Asbestos Screening in Soil"
date: 2026-07-08
draft: false
description: "Linked rotation-assisted microscopy detections to field-of-view, slide, and sample-level screening performance through hierarchical error propagation."
topic: "Sustainability & Environmental Decision Systems"
tags: ["Computer Vision", "Error Propagation", "Environmental Screening"]
provenanceStatus: "verified"
provenanceSources:
  - "https://doi.org/10.1016/j.jhazmat.2026.142934"
  - "https://pubmed.ncbi.nlm.nih.gov/42435689/"
  - "https://github.com/hwcmu/asbestos-plm-screening"
projectType: "Published Research Project"
role: "Lead author · Computer vision · Statistical error propagation"
highlight:
  title: "Evaluate the sample decision, not only the detector"
  text: "The framework propagates field-of-view detection errors through slide and sample consensus rules, making screening performance conditional on the sampling protocol."
supportingHighlights:
  - title: "Optical evidence remains part of the workflow"
    text: "Rotation-assisted paired imaging addresses optical extinction in polarized light microscopy."
  - title: "A negative screen has a defined scope"
    text: "The interpretation depends on detectable-fiber occupancy, background errors, and the evaluated scanning and consensus rules."
doi: "10.1016/j.jhazmat.2026.142934"
codeUrl: "https://github.com/hwcmu/asbestos-plm-screening"
---

## When Does a Detection Support a Screening Decision?

Polarized light microscopy (PLM) produces observations from selected fields of view. A soil-screening decision is made at the sample level. I connected those levels in a chrysotile-focused workflow combining deep learning with statistical error propagation.

The study links a rotation-assisted instance-segmentation pipeline to a hierarchical model of screening performance. This makes the acquisition protocol and aggregation rules part of the evaluation, rather than treating image-level detection performance as sufficient evidence for a sample-level conclusion.

## Preserve the Optical Context

The imaging workflow uses paired observations and rotation-assisted recovery to address optical extinction. The public implementation includes Detectron2-based Mask R-CNN training, single-image and paired-image prediction, and image rotation and difference utilities.

That design ties the model to how microscopy evidence is collected. Performance cannot be assumed to carry over unchanged to other imaging conditions or mineral matrices.

## Propagate Errors Through the Sampling Protocol

The statistical workflow connects three levels:

1. **Field of view:** detectable-fiber occupancy, recall, and false-positive rate.
2. **Slide:** the number of inspected fields and the slide-level consensus rule.
3. **Sample:** the number of slides, sample-level consensus, and assumed prevalence.

These parameters determine how detection errors accumulate or are reduced by repeated observations. The public calculation exposes them explicitly, allowing the screening assumptions to be inspected and changed.

## Report a Bounded Screening Result

The paper develops a protocol-dependent triage interpretation, including cases that call for additional scanning or complementary analysis. A negative screen means that fibers were not detected under the evaluated protocol; it is not an unrestricted claim that a sample is asbestos-free.

The contribution is the connection between model errors and the conditions of a downstream decision. The calculation should not be treated as a universal diagnostic or regulatory threshold.

## What the Public Code Supports

The repository includes the core training, prediction, paired-image, and error-propagation code. It does not redistribute the study images or trained weights. Its linked public dataset is an alternative source whose suitability must be checked, rather than a substitute guaranteed to reproduce the published experiment.

The [published article](https://doi.org/10.1016/j.jhazmat.2026.142934) and [code repository](https://github.com/hwcmu/asbestos-plm-screening) document the method and its scope.
