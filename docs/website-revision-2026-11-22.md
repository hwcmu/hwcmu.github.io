# Website revision — 2026-11-22

Implemented from the supplied website revision guide and its follow-up project text, with claims checked against existing public pages, papers, and repository documentation.

## Page mapping

| Area | Implementation |
| --- | --- |
| Home | Unified research question, three focus areas, project links, collaboration scope |
| Credentials | Completed M.S. in Analytics; M.S. in Computer Science in progress, as confirmed by the author |
| Projects | Three groups; nine unique project entries; date-descending order within each group |
| ESRD, IV fluid, EKG | Contribution-first summaries, explicit outcomes and validation boundaries, links to relevant Notes |
| Sustainability | Updated power-transition and LCA narratives; retained the solar project; added asbestos screening |
| Applied ML | Updated migraine and flight pages while preserving proprietary-data and prototype boundaries |
| Notes | Method Note label for transportability; EKG-first SHAP explanation; numbered SQL review workflow |
| Papers and CV | Added the asbestos Project link alongside canonical DOI and Code links |
| Persona | Unchanged; the single Moonshot Academy reflection remains |

## Evidence corrections to the supplied copy

- IV fluid: the [published abstract](https://api.crossref.org/works/10.7717/peerj-cs.3441) reports five-fold cross-validation. The revised page does not claim independent-test-set calibration. It preserves the reported sample size, representations, and AUC values.
- EKG: the [paper](https://doi.org/10.3390/jpm15080358) supports a retrospective utilization comparison. The page does not claim a validated triage prompt or a verified prospective feature-availability audit.
- ESRD: retain the existing distinction between the chronic-condition indicator and visit diagnoses; avoid interpreting the indicator as independently validated clinical ground truth. Preserve all six reported weighting specifications, including relative risk.
- Asbestos: the [paper](https://doi.org/10.1016/j.jhazmat.2026.142934), [publication metadata](https://pubmed.ncbi.nlm.nih.gov/42435689/), and [public code](https://github.com/hwcmu/asbestos-plm-screening) support a protocol-dependent screening framework. Do not claim universal compliance cutoffs, universally safe negative clearance, calibrated concentration intervals, or measured throughput gains. The code was already released; this update adds its portfolio case study without modifying or republishing the code repository. No private images, weights, or draft materials were needed.
- Power transition: [public documentation](https://github.com/hwcmu/stock-based-power-transition-monitoring) identifies Global Energy Monitor's Global Integrated Power Tracker. Stock substitution measures capacity reallocation, not emissions reductions.
- LCA: the [review](https://doi.org/10.1371/journal.pclm.0000732) is a phase-specific synthesis, not a benchmark establishing the highest return on investment.
- Migraine: retain the documented random-forest and physician-guided design. No public calibration, baseline improvement, retention benefit, or clinical-outcome estimate was added.
- Flight: the [repository](https://github.com/hwcmu/Real-Time-Flight-Delay-Prediction-TabPy-Tableau-NOAA-Integration) distinguishes live temperatures from historical lookup features and displays SHAP explanations for predicted delays. No unreported latency or model-comparison delta was supplied.

## Release checks

- Build Hugo into a temporary destination.
- Check all project groups, chronology, highlights, language controls, and internal links.
- Check that no editorial placeholders reached public text.
- Inspect desktop/mobile and light/dark layouts; exercise topic and tag filters.
- Review touched public text and exact staged paths; exclude unrelated edits and generated output.
- Verify remote main, Pages deployment, and public routes after publication.
