---
title: "Hairong Wang, PhD"
description: "Clinical health data science, real-world data workflows, education, experience, skills, and publications."
hideMeta: true
---

## Summary

Data Analyst at the University of Pittsburgh and Statistician (via IPA) at the U.S. Department of Veterans Affairs. I study the conditions under which real-world data and AI-generated outputs can reliably support decisions in health and sustainability systems.

My work bridges auditable data engineering (SQL, Python, R, ETL pipelines) with biostatistics and applied machine learning—working across structured EHRs, public clinical datasets, short clinical narratives, and environmental sensor data. I focus on turning messy real-world records into analysis-ready cohorts, interpretable models, and reviewer-facing evidence where data provenance, timing, and assumptions hold up under both technical and clinical scrutiny.

---

## Education

- **M.S. in Computer Science** — Georgia Institute of Technology, Atlanta, GA · *Aug 2026 – Present*
- **M.S. in Analytics** — Georgia Institute of Technology, Atlanta, GA · *Aug 2024 – Jul 2026*
- **Ph.D. in Environmental Engineering (Data Science Concentration)** — Carnegie Mellon University, Pittsburgh, PA · *Aug 2021 – Aug 2025*

---

## Work Experience

### Data Analyst · University of Pittsburgh

*May 2026 – Present · Full-time · Pittsburgh, PA*

- **Clinical Research & Operational Analytics:** Support cohort construction, study design, and interpretation using real-world healthcare data; apply regression, survival analysis, clinical NLP, and predictive modeling in R and Python.
- **SQL & Longitudinal Data Workflows:** Extract, clean, and structure longitudinal healthcare data from complex healthcare systems for reproducible research and decision support.
- **VA Assignment — Statistician, U.S. Department of Veterans Affairs (IPA Arrangement):** Support study design, clinical data workflows, statistical analysis, and interpretation as part of my University of Pittsburgh appointment. Projects include the **CLEAR TEAM** multicenter randomized controlled trial.

### Research Health Data Scientist · University of Pittsburgh

*Jan 2026 – May 2026 · Part-time · Pittsburgh, PA*

- **EHR & Clinical NLP:** Analyzed structured EHR data and 13,000+ clinical text records using NLP techniques to support patient-level prediction and clinical decision analysis.
- **Multimodal Prediction:** Built and validated predictive models for IV fluid administration, integrating text and structured features to improve performance over single-modality baselines.
- **Network & Statistical Analysis:** Conducted network analysis and clinical trial–oriented statistical analyses to examine patient characteristics, treatment patterns, and care pathways.

### Research Associate II / Research Associate · Carnegie Mellon University

*Part-time · Pittsburgh, PA · Hybrid*

**Research Associate II** · *Jan 2026 – Apr 2026*

**Research Associate** · *Oct 2025 – Dec 2025*

- **Adaptive Sampling:** Applied Gaussian process regression and active learning to guide environmental sampling and model spatial uncertainty.
- **Power Transition Monitoring:** Analyzed power-plant records to track operating capacity, renewable expansion, and fossil-stock change, distinguishing new capacity additions from replacement of existing assets. ([Power Transition Monitoring](/projects/fossil-persistence-renewable-expansion/))
- **Solar Project Structures:** Used network analysis to compare national utility-scale solar portfolios by project size, development status, project count, and capacity. ([Solar Project Structures](/projects/solar-structural-analytics/))

### Data Scientist · Peachy Day

*Oct 2025 – Dec 2025*

- **Product & Health Data Pipelines:** Built SQL-based pipelines integrating user health logs, weather feeds, and app activity data.
- **Product Analytics & Reporting:** Defined product metrics and developed longitudinal reporting workflows using integrated health and activity data.
- **Forecasting & Personalization:** Developed migraine-risk and recurrent-event modeling workflows with feature attribution, translating model outputs into user-level personalized insights.

---

## Selected Research & Project Experience

- **ESRD Acute-Care Networks:** Constructed multiscale networks linking presenting reasons and diagnoses in emergency encounters, and tested how cohort definitions and edge weights affected the observed clinical structure. ([ESRD Acute-Care Networks](/projects/esrd-acute-encounter-networks/))
- **IV Fluid Utilization Prediction:** Combined structured emergency-care variables with short patient narratives and compared NLP representations for predicting observed IV fluid use, distinguishing utilization from clinical need. ([IV Fluid Utilization Prediction](/projects/iv-fluid-prediction/))
- **EKG Utilization Prediction:** Combined structured clinical variables with Clinical-BERT narrative features, compared separate and combined modalities, and used SHAP and permutation importance to examine predictions of observed EKG use. ([EKG Utilization Prediction](/projects/ekg-utilization-prediction/))
- **Migraine Forecasting & Digital Health Analytics:** Defined core product metrics, built SQL analytics workflows, designed physician-guided migraine forecasting logic, and created longitudinal data-story outputs for user engagement. ([Migraine Forecasting](/projects/migraine-prediction/))
- **Doctoral Research · Carnegie Mellon University:** Developed Mask R-CNN, Gaussian process regression, active learning, and geospatial modeling workflows for environmental sensing and field screening. Built hierarchical statistical frameworks to quantify how model and measurement errors propagate into downstream environmental and infrastructure decisions. ([Asbestos Screening](/projects/asbestos-plm-screening/) · [Asbestos DOI](https://doi.org/10.1016/j.jhazmat.2026.142934))
- **Applied ML & Real-Time BI Systems:** Engineered a live flight-delay prediction pipeline linking historical flight records, NOAA weather APIs, Python/TabPy inference, and an interactive Tableau dashboard with SHAP explanations for predicted delays. ([Flight Delay Prediction Dashboard](/projects/airport-prediction/))

---

## Skills

- **Healthcare Data & RWD:** EHR & clinical data analysis, clinical narratives, cohort construction, analytic dataset design, NHAMCS-ED, clinical trial support, real-world data auditing.
- **Programming & Data Engineering:** Python (Pandas, NumPy, Scikit-learn), R, SAS, SQL, ETL pipelines, data cleaning, reproducible research workflows, dashboard reporting.
- **Statistical Modeling:** Descriptive & inferential statistics, hypothesis testing, linear & logistic regression, GLMs, mixed-effects models, recurrent-event survival analysis, Bayesian & experimental design.
- **Machine Learning & Clinical NLP:** XGBoost, gradient boosting, Mask R-CNN, Gaussian process regression, active learning, clinical NLP & multimodal modeling, model evaluation & calibration, explainable AI (SHAP, permutation importance).
- **Visualization & Communication:** Matplotlib, Tableau / TabPy, manuscript preparation, reviewer-response evidence packages, interdisciplinary technical documentation.

**Selected Graduate Coursework:** Big Data for Healthcare; Computing for Data Systems; Natural Language Processing; Computational Data Analytics; High-Dimensional Data Analytics; Data and Visual Analytics; Simulation; Regression Analysis; Generalized Linear Models; Machine Learning; Bayesian Statistics; Experimental Design; Survival Modeling.

---

## Selected Publications

*Six selected works aligned with clinical AI, real-world data, and sustainability systems. Full list of 13 peer-reviewed publications available on [Google Scholar](https://scholar.google.com/citations?user=omqwO78AAAAJ&hl=en) and the [Papers](/publications/) page.*

### Healthcare Data Science

1. **Wang, H.**, & Zhang, X. (2026). Mapping acute encounters in end-stage renal disease: a multi-scale network analysis of presenting reasons and diagnoses. *Network Modeling Analysis in Health Informatics and Bioinformatics*, 15, 164. ([DOI](https://doi.org/10.1007/s13721-026-00848-7) · [ESRD Acute-Care Networks](/projects/esrd-acute-encounter-networks/))
2. **Wang, H.**, Ling, H., & Zhang, X. (2025). Integrating multimodal clinical data to predict intravenous (IV) fluid utilization: a comparative analysis of natural language processing techniques. *PeerJ Computer Science*, 11, e3441. ([DOI](https://doi.org/10.7717/peerj-cs.3441) · [Code](https://github.com/hwcmu/IVF-prediction) · [IV Fluid Utilization Prediction](/projects/iv-fluid-prediction/))
3. **Wang, H.**, & Zhang, X. (2025). Machine Learning for Personalized Prediction of Electrocardiogram (EKG) Use in Emergency Care. *Journal of Personalized Medicine*, 15(8), 358. ([DOI](https://doi.org/10.3390/jpm15080358) · [Code](https://github.com/hwcmu/EKG-prediction) · [EKG Utilization Prediction](/projects/ekg-utilization-prediction/))

### Environmental & Sustainability Data Science

1. **Wang, H.**, Hong, C., & Sun, J. (2026). Beyond megawatts: Structural configurations and project ecologies in global utility-scale solar. *Energy, Ecology and Environment*. ([DOI](https://doi.org/10.1007/s40974-026-00428-5) · [Code](https://github.com/hwcmu/global-solar-project-ecologies) · [Solar Project Structures](/projects/solar-structural-analytics/))
2. **Wang, H.**, Piao, W., Hoelen, T. P., & Lowry, G. V. (2026). Deep learning-assisted chrysotile asbestos screening in soil: A hierarchical statistical approach to error propagation. *Journal of Hazardous Materials*, 514, 142934. ([DOI](https://doi.org/10.1016/j.jhazmat.2026.142934) · [Code](https://github.com/hwcmu/asbestos-plm-screening) · [Asbestos Screening](/projects/asbestos-plm-screening/))
3. **Wang, H.**, & Hong, C. (2026). A stock-based framework for monitoring fossil persistence and renewable expansion in global power systems. *Energy, Ecology and Environment*. ([DOI](https://doi.org/10.1007/s40974-026-00425-8) · [Code](https://github.com/hwcmu/stock-based-power-transition-monitoring) · [Power Transition Monitoring](/projects/fossil-persistence-renewable-expansion/))
