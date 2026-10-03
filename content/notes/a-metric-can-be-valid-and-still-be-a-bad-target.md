---
title: "A Metric Can Be Valid and Still Be a Bad Target"
date: 2026-10-03
draft: false
contentType: "reading-note"
sourceBook: "Irresistible"
sourceBookZh: "欲罢不能"
description: "Why measurement validity does not guarantee that a metric remains useful after people or systems begin optimizing it."
url: "/blogs/a-metric-can-be-valid-and-still-be-a-bad-target/"
series: ["Boundary Notes", "Modeling Decisions"]
tags: ["Measurement", "Goodhart's Law", "Clinical Endpoints"]
provenanceStatus: "verified"
provenanceSources:
  - "https://www.penguinrandomhouse.com/books/318516/irresistible-by-adam-alter/9780735222847/"
  - "https://doi.org/10.1017/S1062798700002660"
  - "https://doi.org/10.1002/sim.4780080407"
  - "https://www.fda.gov/drugs/development-resources/surrogate-endpoint-resources-drug-and-biologic-development"
---

A daily step target can be a useful prompt to move. A streak can help someone return to a language lesson. Engagement can show that a product is not being ignored.

None of those observations makes the metric the purpose of the activity.

One of the most useful ideas I took from *Irresistible* is what I call **target alienation**: a target created to serve a behavior gradually becomes the rule that the behavior must serve.

The statistical version is sharper:

> A metric can measure something consistently and still become a bad objective once a system begins optimizing it.

## Measurement and Optimization Are Different Jobs

A metric can play at least three roles:

1. **Description:** What happened?
2. **Decision support:** Is intervention or investigation warranted?
3. **Optimization target:** What should the system maximize or minimize?

Evidence that supports the first role does not automatically support the third.

A step count may describe movement reliably without fully representing health. Session length may describe product use without representing benefit. A biomarker may predict a clinical outcome without guaranteeing that changing the biomarker through treatment will change that outcome.

The transition from measure to target changes the system around the measure.

## The Target Changes the Data-Generating Process

Before a measure becomes a target, it records behavior. After it becomes a target, people and systems adapt to it.

They may:

- redirect effort toward what is counted;
- choose easier cases that improve the score;
- move activity across a reporting boundary;
- preserve the metric while sacrificing an unmeasured outcome;
- learn to produce the appearance of success.

This is the practical force behind Goodhart-type failures. The problem is not simply that the metric was noisy. Optimization creates a new data-generating process in which the old relationship between metric and purpose may weaken.

## Clinical Surrogates Show the Boundary Clearly

Clinical trials sometimes use a surrogate endpoint instead of directly measuring how a patient feels, functions, or survives. That substitution can make an otherwise impractical study possible.

But association is not enough. A biomarker can correlate strongly with a clinical outcome while failing to capture all the pathways through which treatment affects that outcome. This is why surrogate validation requires evidence about treatment effects, not merely predictive accuracy.

The distinction is:

| Question | Evidence needed |
| --- | --- |
| Does the marker predict the clinical outcome? | Prognostic association and validation |
| Does changing the marker improve the clinical outcome? | Treatment-level evidence that the surrogate captures relevant effects |

The same boundary appears outside medicine. Predicting satisfaction from engagement does not establish that maximizing engagement will increase satisfaction.

## A Dashboard Can Reverse the Direction of Control

*Irresistible* describes how goals, streaks, scores, and visible feedback can sustain behavior. That can be useful when motivation is low and the target remains subordinate to a real purpose.

The failure begins when an internal stopping signal is overruled by an external number:

- continuing to exercise despite pain because the step target is incomplete;
- preserving a learning streak with meaningless activity;
- increasing notifications because daily active use is rewarded;
- favoring easy-to-measure outputs over difficult but valuable work.

The metric has not necessarily become inaccurate. It has become authoritative beyond the evidence supporting it.

## Review the Objective, Not Just the Metric

Before optimizing a measure, document:

1. **Purpose:** What real outcome is the measure supposed to serve?
2. **Proxy:** Which part of that outcome does it capture, and what does it omit?
3. **Response:** How will people or algorithms change when rewarded on it?
4. **Guardrails:** Which harms or displaced outcomes must be monitored separately?
5. **Stopping rule:** At what point does more cease to be useful?
6. **Revalidation:** How will we test whether the proxy-purpose relationship survives optimization?

This review is different from checking whether a metric is calculated correctly. A perfectly implemented metric can still produce a badly directed system.

## The Boundary

The answer is not to abandon metrics. Decisions without measurement are vulnerable to memory, hierarchy, and intuition. The answer is to keep the metric in its proper role.

Use several measures when the objective has several dimensions. Pair leading indicators with outcomes and harms. Revalidate after incentives change. Preserve room for judgment when the construct cannot be reduced to one number.

Efficiency cannot decide whether total activity should keep expanding. The companion problem here is that measurement cannot decide what deserves to become the objective.

> The question is not only whether the number is valid. It is whether the system remains valid after the number gains power over it.

## Sources

- Alter A. [*Irresistible: The Rise of Addictive Technology and the Business of Keeping Us Hooked*](https://www.penguinrandomhouse.com/books/318516/irresistible-by-adam-alter/9780735222847/). Penguin Press.
- Strathern M. ["Improving Ratings": Audit in the British University System](https://doi.org/10.1017/S1062798700002660). *European Review*. 1997.
- Prentice RL. [Surrogate Endpoints in Clinical Trials: Definition and Operational Criteria](https://doi.org/10.1002/sim.4780080407). *Statistics in Medicine*. 1989.
- U.S. Food and Drug Administration. [Surrogate Endpoint Resources for Drug and Biologic Development](https://www.fda.gov/drugs/development-resources/surrogate-endpoint-resources-drug-and-biologic-development).
