---
title: "A Causal Story Must Predict a Different Curve"
date: 2026-08-29
draft: false
contentType: "reading-note"
sourceBook: "The Molecule of More"
sourceBookZh: "贪婪的多巴胺"
description: "How competing explanations become testable when they imply different dose-response shapes, time courses, controls, or response allocations."
url: "/blogs/a-causal-story-must-predict-a-different-curve/"
series: ["Research Workflow Notes", "Modeling Decisions"]
tags: ["Causal Inference", "Experimental Design", "Identifiability"]
provenanceStatus: "verified"
provenanceSources:
  - "https://doi.org/10.1126/science.146.3642.347"
  - "https://doi.org/10.1086/607980"
  - "https://doi.org/10.1007/BF02245659"
  - "https://doi.org/10.1016/S0306-4522(01)00249-4"
---

A dataset can support a striking association and still tell us almost nothing about which explanation produced it.

Suppose an intervention is followed by less effort. One story says the intervention reduced motivation. Another says it reduced the value of the reward. A third says it impaired movement. If all three predict the same average decline, a smaller p-value does not separate them.

The study has measured an effect without identifying its mechanism.

> A causal story becomes scientifically useful when it predicts an observation that its competitors do not.

Sometimes that observation is a different group. Sometimes it is a different time order, threshold, negative control, or dose-response shape. The point is not that every mechanism must produce a smooth curve. The point is that competing stories must be forced to disagree somewhere observable.

## The Rat Did Less Work. Why?

A series of experiments on nucleus accumbens dopamine and effort offers a clean example.

Food-deprived rats could press a lever for a preferred food pellet or eat less-preferred laboratory chow that was freely available. After dopamine interference, lever pressing fell. Taken alone, that result admits several stories:

- the rats no longer valued food;
- the rats could no longer perform the response;
- the rats still wanted food but reallocated behavior away from the higher-effort option.

The useful evidence was not simply "lever pressing decreased." It was the pattern across alternatives and controls.

Pre-fed rats reduced both lever pressing and free-food consumption, consistent with lower food motivation. Rats receiving dopamine interference pressed less but ate more of the freely available chow. Their behavior remained directed toward food; the allocation of effort changed.

Later fixed-ratio experiments varied how many presses were required for reinforcement. Dopamine-depleted rats showed relatively small or transient effects at low ratios and much larger impairment as the work requirement increased. The response was shaped by cost.

The two explanations therefore predicted different response surfaces:

| Explanation | Lever pressing | Free chow | Sensitivity to higher work requirement |
| --- | --- | --- | --- |
| Lower food value or appetite | Down | Down | Not the defining prediction |
| Altered effort allocation | Down | Up or preserved | Increasing impairment as ratio rises |

This does not prove that one neurotransmitter has one simple psychological function. It shows something narrower and stronger: **alternative explanations can be separated when the design makes them predict different patterns.**

## A Mean Difference Is Often the Least Discriminating Result

Researchers often ask whether an association exists. A better design question is: *What form should the data take if this mechanism is true?*

Different mechanisms may imply different signatures:

| Design dimension | Competing prediction |
| --- | --- |
| Dose or exposure | Linear increase, threshold, plateau, U-shape, or no gradient |
| Time | Immediate response, delayed response, cumulative change, or reverse ordering |
| Subgroup | Stronger where the mechanism is present; absent where it cannot operate |
| Alternative behavior | Global suppression versus reallocation toward a lower-cost option |
| Negative control | Association where the mechanism predicts none suggests bias or confounding |
| Intervention | Changing the proposed mediator should alter the outcome in the predicted direction |

A useful curve is not necessarily literal. "Curve" is shorthand for a structured pattern across conditions.

The researcher's job is to identify the condition under which the stories stop looking alike.

## Write the Competing-Predictions Table Before the Model

This reasoning is older than modern causal-inference software. Chamberlin argued for multiple working hypotheses rather than attachment to one favored explanation. Platt's "strong inference" similarly emphasized alternative hypotheses and experiments designed to exclude them.

The practical version is a one-page table written before analysis:

| Hypothesis | What it explains | Unique prediction | Best discriminator | What would weaken it? |
| --- | --- | --- | --- | --- |
| H1 | Observed association | Pattern A | Control or contrast A | Pattern B appears |
| H2 | Same association | Pattern B | Dose, time, or subgroup B | Pattern A appears |
| H3: bias | Same association | Negative-control signal | Negative control | No bias signature |

This table changes the workflow in several ways.

1. It exposes explanations that are merely verbal restatements of the result.
2. It prevents the analyst from choosing the most flattering interpretation after seeing the data.
3. It reveals when the available dataset cannot identify the desired mechanism.
4. It tells the team which new measurement or experiment would be most informative.

The table is especially useful before fitting a flexible model. Machine learning can estimate a complex response surface, but it cannot decide which contrasts were theoretically diagnostic after the fact.

## Shape Alone Does Not Establish Causality

A dose-response gradient, threshold, or temporal pattern can discriminate among stated hypotheses. It can also be produced by confounding, selection, measurement error, model specification, or an omitted fourth mechanism.

Three safeguards matter.

### Specify the prediction before inspecting the result

If every observed shape receives a new story afterward, the theory never risks being wrong. Pre-specification need not mean a registered trial for every exploratory analysis. It means recording what each hypothesis predicted before allowing the result to rewrite the prediction.

### Measure the discriminating variable well

A threshold claim is weak when exposure is heavily misclassified. A time-course claim is weak when event timing is coarse. A subgroup interaction is weak when the subgroup was created after searching many alternatives.

### Keep explanation and identification separate

A mechanistic narrative can motivate a contrast. Identification still depends on the design: randomization, exchangeability assumptions, valid controls, temporal ordering, and an appropriate analysis population.

The curve is evidence between hypotheses only under those conditions.

## A Better Question for Observational Research

When two explanations fit the same association, do not immediately ask for a larger sample. Ask for a sharper disagreement.

- Which outcome should change first?
- Where should the effect disappear?
- What low-cost alternative should behavior shift toward?
- Which negative control should remain null?
- What dose-response form does each mechanism predict?
- What observation would make my preferred explanation less plausible?

More data help when they measure the contrast that matters. More rows of the same non-discriminating variables mainly make the ambiguity more precise.

> Evidence is not strong because the curve is smooth. It is strong when plausible rival stories expected the curve to look different.

That is the move from describing a pattern to testing an explanation.

## Sources

- Chamberlin TC. [Studies for Students: The Method of Multiple Working Hypotheses](https://doi.org/10.1086/607980). *The Journal of Geology*. 1897.
- Platt JR. [Strong Inference](https://doi.org/10.1126/science.146.3642.347). *Science*. 1964.
- Salamone JD, et al. [Haloperidol and nucleus accumbens dopamine depletion suppress lever pressing for food but increase free food consumption in a novel food choice procedure](https://doi.org/10.1007/BF02245659). *Psychopharmacology*. 1991.
- Salamone JD, et al. [Nucleus accumbens dopamine depletions make animals highly sensitive to high fixed ratio requirements but do not impair primary food reinforcement](https://doi.org/10.1016/S0306-4522(01)00249-4). *Neuroscience*. 2001.
