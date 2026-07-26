---
title: "Simulation Is Becoming Medicine's Experimental Layer"
date: 2026-07-26
draft: false
description: "Why the next phase of medical AI may depend on hybrid simulators, virtual patients, and models that can test interventions rather than merely predict outcomes."
url: "/blogs/simulation-medicine-experimental-layer/"
series: ["Future of Medical AI", "Boundary Notes"]
tags: ["Medical Simulation", "Clinical AI", "Digital Twins"]
---

Most medical AI is trained to look backward. It learns from patients who have already been observed and predicts a label: deterioration, readmission, treatment response, or diagnostic probability.

But many of medicine's hardest questions are not prediction questions.

What happens if the dose changes? Which tissue should be ablated? How would a device perform in an anatomy that was rare in the original trial? What if a hospital changes its staffing or triage policy?

These are intervention questions. Historical data alone contain only the actions that were actually taken. Simulation adds something different: a controlled world in which alternative actions can be tried before they reach a patient.

> The next important layer of medical AI may not be another predictor. It may be an environment in which predictions can be turned into experiments.

## The Earlier Form of Simulation

Traditional simulation begins with a mechanism written by the modeler.

In a classroom flu model I built, one infectious student entered a group of susceptible classmates. Transmission probability, infectious duration, immunity, and the contact structure were specified in advance. The model was then repeated thousands of times to estimate an outcome distribution.

The first check was analytical:

$$
X_1 \sim \operatorname{Binomial}(60, 0.01),
\qquad E[X_1] = 0.60.
$$

If the simulated first-day mean did not approach `0.60` over enough replications, the code was wrong. This is still a good verification habit. A simulation should survive simple equations, edge cases, and conservation checks before its larger results are trusted.

But this older form has a clear shape:

```text
hand-specified mechanism -> fixed parameters -> repeated runs -> output distribution
```

It is transparent, but usually generic. The model does not learn from a particular patient, update itself as new measurements arrive, or fill gaps where the biology is only partly understood.

Medical AI changes each of those possibilities.

## Simulation Is Already Part of Medical Evidence

This direction is not purely speculative.

In drug development, pharmacokinetic, pharmacodynamic, and physiologically based models are already used to connect dose, exposure, efficacy, and safety. The FDA's final [ICH M15 guidance](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/m15-general-principles-model-informed-drug-development), issued in June 2026, provides a framework for planning, evaluating, and documenting model-informed drug development evidence.

In medical devices, computational models can complement bench, animal, and clinical evidence. The FDA has also published a [risk-informed credibility framework](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/assessing-credibility-computational-modeling-and-simulation-medical-device-submissions) for physics-based and mechanistic simulations used in device submissions.

The VICTRE project offers a tangible example. Researchers constructed virtual breast anatomies, inserted lesions, simulated image acquisition, and compared digital mammography with digital breast tomosynthesis inside an in silico imaging trial. The point was not to generate attractive synthetic images. It was to recreate enough of the imaging chain to evaluate a specific technology question.

Simulation in medicine therefore already operates at several levels:

- **Drug and dose models** connect biological mechanisms with treatment exposure.
- **Virtual trials** test products or study designs across simulated populations.
- **Device and imaging models** reproduce physical interactions that are expensive or difficult to observe directly.
- **Workflow simulations** compare patient flow, staffing, capacity, and operational policies.
- **Patient-specific models** rehearse an intervention on a virtual representation before acting on the real patient.

The future lies less in choosing one of these categories than in connecting them.

## AI and Simulation Solve Opposite Problems

Traditional simulation is strongest where mechanisms are known but often struggles where parameters are difficult to measure. Machine learning is strongest where data are abundant but often struggles to extrapolate beyond the patterns it has observed.

Their relationship is therefore complementary.

**AI can strengthen simulation by:**

- estimating patient-specific parameters from imaging, laboratory, genomic, or sensor data;
- learning residual relationships that are missing from a mechanistic model;
- approximating computationally expensive solvers with faster surrogate models; and
- generating heterogeneous virtual cohorts for stress testing.

**Simulation can strengthen AI by:**

- providing structured environments for testing interventions;
- enforcing physiological constraints such as mass balance, anatomy, or feasible state transitions;
- exposing models to rare but clinically important scenarios; and
- separating a model's apparent performance from the assumptions that produced it.

A useful hybrid form is:

$$
x_{t+1}
=
f_{\text{mechanism}}(x_t, u_t; \theta_i)
+
r_{\text{AI}}(x_t, u_t, d_i),
$$

where the mechanistic component represents known physiology, `u_t` is an intervention, patient data `d_i` help personalize the parameters, and the AI component learns what the mechanistic model does not capture well.

This is more promising than asking a black-box model to learn the entire clinical world from records alone. In one published pharmacokinetic example, deep learning predicted molecular properties while a physiologically based model propagated those properties into concentration-time profiles. The AI supplied flexibility; the mechanistic model supplied a structure that could support extrapolation.

## From Population Models to Patient-Specific Experiments

The most interesting progression is not simply toward larger simulations. It is toward more individualized and more continuously updated ones.

```mermaid
flowchart LR
    A["Population simulation"] --> B["Virtual cohort"]
    B --> C["Patient-specific model"]
    C --> D["Digital twin"]
    D --> E["Closed-loop learning system"]
```

A **population simulation** asks how a mechanism behaves under different assumptions. A **virtual cohort** introduces variation across many simulated patients. A **patient-specific model** is calibrated to one person's anatomy or physiology. A true **digital twin** should also be updated when new observations arrive. A closed-loop system goes further by comparing actions, observing the result, and recalibrating the next decision.

Cardiac electrophysiology shows what this direction might look like. In a 2026 feasibility study, patient-specific heart models were used to identify ventricular-tachycardia ablation targets before the procedures. Ventricular tachycardia was noninducible after ablation in all 10 participants; at a mean follow-up of 13 months, eight were recurrence-free without antiarrhythmic medication.

That is an unusually vivid example of simulation moving from retrospective analysis into treatment planning. It is also a small feasibility study, not proof that digital twins are ready for routine use across medicine.

## A Plausible Synthetic Patient Is Not Yet a Simulator

Generative AI makes it easy to produce realistic-looking records, conversations, trajectories, and patient profiles. That can be useful for education, software testing, controlled development without operational records, or data augmentation.

But realism is not the same as intervention validity.

A language model may generate a plausible sequence of laboratory results after a medication change without representing the causal and physiological processes that connect the drug to those results. Such a model can imitate a patient record while failing as a virtual patient.

For a simulator to support a medical decision, it needs more than plausibility:

1. a clearly defined **context of use**;
2. an intervention that changes the model through a defensible mechanism;
3. calibration to the population or patient being represented;
4. uncertainty that expands when the model leaves its evidence base; and
5. validation against outcomes that matter for the intended decision.

This is the central boundary for AI-era simulation:

> A model becomes medically useful not when it can generate a believable future, but when it can distinguish which futures its evidence allows it to compare.

## The First Equation Still Matters

The old flu simulation belongs to an earlier form of the field, but its lesson has not disappeared. Verification still begins with simple expectations, invariants, and edge cases.

What has changed is the size of the credibility question.

For an AI-enabled medical simulator, we must now ask:

- Did the code implement the model?
- Does the model represent the relevant mechanism?
- Can the patient-specific parameters actually be identified?
- Does the simulated intervention correspond to a real clinical action?
- How does uncertainty propagate into the recommended decision?
- When new data disagree with the twin, which one changes?

Ten thousand runs cannot rescue a wrong mechanism. Neither can a foundation model.

The future of medical AI may be less about predicting one outcome from one record and more about building constrained experimental worlds: places where drugs, devices, workflows, and treatments can be tested virtually, uncertainty remains visible, and real-world feedback keeps the model honest.

## Sources

- U.S. Food and Drug Administration. [Modeling & Simulation at FDA](https://www.fda.gov/science-research/about-science-research-fda/modeling-simulation-fda).
- U.S. Food and Drug Administration. [M15 General Principles for Model-Informed Drug Development](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/m15-general-principles-model-informed-drug-development). Final guidance, June 2026.
- U.S. Food and Drug Administration. [Assessing the Credibility of Computational Modeling and Simulation in Medical Device Submissions](https://www.fda.gov/regulatory-information/search-fda-guidance-documents/assessing-credibility-computational-modeling-and-simulation-medical-device-submissions). Final guidance, November 2023.
- Sharma D, Graff CG, Badal A, et al. [In Silico Imaging Tools from the VICTRE Clinical Trial](https://doi.org/10.1002/mp.13674). *Medical Physics*. 2019;46(9):3924-3928.
- Gruber A, Führer F, Menz S, et al. [Prediction of Human Pharmacokinetics from Chemical Structure: Combining Mechanistic Modeling with Machine Learning](https://doi.org/10.1016/j.xphs.2023.10.035). *Journal of Pharmaceutical Sciences*. 2024.
- Chrispin J, Prakosa A, Kholmovski E, et al. [Digital Twin-Guided Ablation for Ventricular Tachycardia](https://doi.org/10.1056/NEJMc2517822). *New England Journal of Medicine*. 2026;394:1345-1347.
