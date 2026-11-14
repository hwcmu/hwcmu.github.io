---
title: "A Model Predicts Well. Why Is That Not Enough? (2/3)"
subtitle: "Accuracy is persuasive because it looks like understanding. The two are not the same."
description: "A reflection on prediction, mechanism, and why a successful model may still fail when the world around it changes."
date: 2026-11-14
draft: false
contentType: "reading-note"
sourceBook: "Scale"
sourceBookZh: "规模"
url: "/persona/when-prediction-is-not-enough/"
translationUrl: "/zh/persona/when-prediction-is-not-enough/"
translationLabel: "中文"
translationCta: "Read in Chinese"
series: ["Persona", "Scale in the AI Age"]
tags: ["AI", "Healthcare", "Scientific Reasoning"]
provenanceStatus: "verified"
provenanceSources:
  - "https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/"
  - "https://pubmed.ncbi.nlm.nih.gov/9082983/"
  - "https://doi.org/10.1214/10-STS330"
  - "https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002683"
build:
  list: never
  render: always
---

There is a moment in almost every modeling project when a number takes over the room. The validation score is better than expected. The curve looks clean. A messy problem suddenly feels settled.

I understand the relief. A good prediction is concrete. It gives us something to compare, optimize, and defend. But it also tempts us to make a quiet substitution: the model predicted well, therefore the model understood the problem.

That substitution is where trouble begins.

## Why *Scale* Keeps Asking "Why?"

In Geoffrey West's *Scale*, one of the most memorable patterns is the relationship between metabolic rate and body mass. Across many organisms, the exponent has often been described as close to three quarters. A large and complicated biological world appears to collapse onto a simple line.

West did not treat that line as the final answer. With James Brown and Brian Enquist, he proposed a model based on space-filling transport networks, relatively invariant terminal units, and minimized energy dissipation. The model has been debated, as scientific mechanisms should be. Its value was not that it ended the conversation. It made the assumptions visible enough for the conversation to continue.

This is what a mechanism adds to a prediction. It gives us a reason the relationship might persist, other consequences that should follow, and places where the pattern ought to break.

A fitted slope tells us what repeated in the observed data. A mechanism asks why it repeated.

## Prediction Has Its Own Legitimate Job

None of this means prediction is scientifically inferior. Statistician Galit Shmueli has argued that prediction and explanation are different modeling goals. A variable can help predict without being a cause. A causal factor can matter deeply while adding little to short-term predictive accuracy.

We use useful predictions without complete explanations all the time. Weather forecasts work before we inspect every atmospheric process. A spam filter does not need a theory of human deception to keep junk out of an inbox.

The difficulty is knowing when prediction is enough.

For a stable, low-stakes task, repeated predictive performance may be the result that matters. But when a model moves between hospitals, influences treatment, or enters an environment that changes over time, we begin asking the model to travel. A score from yesterday's setting becomes a claim about tomorrow's setting.

That claim needs more than accuracy.

## The Hospital Hidden Inside the Image

A 2018 study of pneumonia detection from chest radiographs remains a useful warning. Models trained across different hospital systems did not generalize uniformly. The models could also identify where an image had been acquired with very high accuracy.

That finding is unsettling because the model may be right for a mixture of reasons. Some image features may reflect disease. Others may reflect equipment, image-processing choices, patient selection, or local workflow. Inside the prediction sits a small portrait of the hospital that produced the data.

As long as the portrait and the outcome remain correlated, the model can look excellent. Move it elsewhere and the shortcut may stop working.

The model did not make a silly mistake. It did exactly what optimization asked: use whatever stable signal was available in the training environment. The mistaken assumption belonged to us. We treated performance within that environment as evidence of understanding beyond it.

## Accuracy Feels Like Closure

I think this is why the distinction is emotionally difficult. Mechanistic uncertainty is uncomfortable. It leaves the project open. A metric offers closure.

AI intensifies that attraction. Modern systems can absorb more variables than we can inspect, discover interactions we did not anticipate, and produce confident outputs at a speed that feels like comprehension. The better the interface becomes, the easier it is to forget that fluency and accuracy answer narrow questions.

A model can tell us that a person resembles previous high-risk cases. It does not automatically tell us what would happen if we intervened, why the risk arose, or whether the same resemblance will matter in a different hospital.

Those are not criticisms of prediction. They are reminders to name the job correctly.

## What Kind of Success Did We Observe?

After a model succeeds, I now think the most useful response is neither blind trust nor a ritual demand for explainability. It is to slow down and classify the success.

Did the model recognize a repeatable pattern in one data pipeline? Did it remain calibrated over time? Did it travel to another institution? Does its explanation describe model behavior or a process in the world? Would the relationship survive an intervention?

Each question asks for different evidence.

Accuracy is a real achievement. It is simply not a permission slip for every stronger claim we would like to make.

The deeper lesson I took from *Scale* is not that every pattern needs one grand theory. It is that a pattern becomes more useful when we understand the conditions holding it together. Prediction tells us that something worked. Mechanism helps us ask whether it should keep working after the world changes.

## Sources and Further Reading

- Geoffrey West. [*Scale*](https://www.penguinrandomhouse.com/books/314049/scale-by-geoffrey-west/). Penguin Books.
- West GB, Brown JH, Enquist BJ. [A General Model for the Origin of Allometric Scaling Laws in Biology](https://pubmed.ncbi.nlm.nih.gov/9082983/). *Science*. 1997.
- Shmueli G. [To Explain or to Predict?](https://doi.org/10.1214/10-STS330). *Statistical Science*. 2010.
- Zech JR, et al. [Variable Generalization Performance of a Deep Learning Model to Detect Pneumonia in Chest Radiographs](https://journals.plos.org/plosmedicine/article?id=10.1371/journal.pmed.1002683). *PLOS Medicine*. 2018.
