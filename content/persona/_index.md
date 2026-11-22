---
title: "Persona"
description: "Reflective notes and topic filters for how I think and work."
hideMeta: true
url: "/persona/"
translationKey: "persona"
---

<div class="topic-explorer">
  <h3>Explore by Topics</h3>
  <div class="topic-tag-row" aria-label="Filter persona entries by topic">
    <button class="topic-tag topic-filter active" type="button" data-tag="all">All</button>
    <button class="topic-tag topic-filter" type="button" data-tag="ai-education">AI Education</button>
    <button class="topic-tag topic-filter" type="button" data-tag="human-agency">Human Agency</button>
    <button class="topic-tag topic-filter" type="button" data-tag="cognitive-offloading">Cognitive Offloading</button>
  </div>
</div>

<div class="persona-list" id="persona-list">
  <article class="persona-entry topic-entry" data-topic-entry data-date="2026-06-28" data-skin="learning" data-pattern="learning-lines" data-series="ai-education" data-tags="ai-education human-agency cognitive-offloading" data-text="ai answer cognitive offloading judgment desire wanting moonshot academy self education human agency">
    <p class="persona-entry-series">AI Education · Moonshot Academy</p>
    <h3><a href="/persona/now-that-ai-can-answer/">Now That AI Can Answer, What Should We Still Train Ourselves To Do?</a></h3>
    <p>A bilingual reflection on AI, survey evidence, and which tasks we still want to practice ourselves.</p>
    <div class="topic-tag-row persona-entry-tags">
      <button class="topic-tag topic-filter" type="button" data-tag="ai-education">AI Education</button>
      <button class="topic-tag topic-filter" type="button" data-tag="human-agency">Human Agency</button>
      <button class="topic-tag topic-filter" type="button" data-tag="cognitive-offloading">Cognitive Offloading</button>
    </div>
  </article>
</div>

<p class="topic-empty persona-empty" hidden>No matching reflections yet.</p>

---

## Before Clinical Data: Notes from the Physical World

Before I moved into clinical EHRs and health AI, my PhD at Carnegie Mellon started in physical environmental systems—brine desalination, autonomous soil-sampling robots, field sensors, and materials research. Because those papers sit outside my current healthcare focus, I keep them off my main project list. Even so, they are where most of my instincts about real-world data and system boundaries came from.

### 1. Desalination and the Cost of What Gets Left Behind

Freshwater scarcity makes desalination sound like a clean engineering victory: take ocean water in, get drinking water out. Once you actually work on concentrated brines, the problem looks much less heroic and much more like a negotiation with thermodynamics. Salt dissolves into water spontaneously; separating them back out always demands an energy bill.

What stayed with me from working on temperature-swing solvent extraction was the stream left behind. Conventional desalination pushes clean water out one end while concentrating a heavier, saltier brine at the other—an environmental burden that still has to go somewhere. Spending time with that constraint left me with a durable heuristic: engineering rarely erases a difficulty. Usually, it concentrates the difficulty and forces a decision about who, or what, absorbs the residue.

Clinical data works the same way. Pulling a tidy analytic cohort out of a messy electronic health record always leaves a residue behind: missing measurements, patients excluded by a coding rule, unrecorded confounders. Optimizing the yield is only half the work; the other half is accounting for what got filtered out.

**Links:** [Paper — *Desalination* (2022)](https://doi.org/10.1016/j.desal.2022.116104)

---

### 2. Field Robotics and the Friction of Measurement

Later in my PhD, I collaborated with robotics and environmental teams on autonomous soil sampling and robot-deployable sensors for screening petroleum hydrocarbons in the field. In a benchmark dataset, numbers arrive neatly aligned in a CSV. Outdoors, obtaining a useful reading depends on the soil, the sampling method, and whether a sensor's calibration holds beyond the conditions in which it was developed.

Watching hardware struggle to capture a single reliable reading permanently changes how you look at a table of data. You stop reading a column as ground truth and start reading it as the output of a fallible instrument operating under real-world friction. Healthcare records carry the exact same friction, just buried inside software—billing codes lag behind clinical reality, lab orders reflect local hospital habits, and timestamps slip. Most downstream modeling errors I audit today begin right there, at the moment of measurement.

**Links:** [Paper — Autonomous Soil Sampling (*J. Environ. Manage.*, 2024)](https://doi.org/10.1016/j.jenvman.2024.121130) · [Paper — Field TPH Sensing (*J. Hazard. Mater.*, 2026)](https://doi.org/10.1016/j.jhazmat.2026.141208)

---

### 3. Intervening Without Breaking the Host

Two other projects—reviewing microbial calcium carbonate precipitation for historical architecture restoration, and testing high-aspect-ratio polymer nanocarriers for gene delivery in plants—looked completely unrelated on the surface. Both, however, run into the same physical boundary: you are introducing an external intervention into a fragile, living or aging structure. An incompatible repair can cause further cracking; a nanocarrier that delivers its payload while damaging leaf tissue would defeat its own purpose.

That same boundary shows up every time an AI model enters a hospital. Training a classifier with high discrimination is relatively straightforward; embedding it into a clinical workflow without triggering alert fatigue, shifting clinician behavior, or distorting care is the actual hard problem. A useful intervention has to respect the scale and tolerance of the system it enters.

**Links:** [Paper — Historical Stone Restoration (*J. Infrastruct. Preserv. Resil.*, 2025)](https://doi.org/10.1186/s43065-025-00125-3) · [Paper — Plant Gene Nanocarriers (*Nano Letters*, 2025)](https://doi.org/10.1021/acs.nanolett.4c04704)

---

*For the full chronological list of my work across clinical AI, energy systems, and environmental engineering, see the [Papers](/publications/) page.*
