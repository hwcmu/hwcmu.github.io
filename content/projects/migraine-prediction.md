---
title: "AI-Powered Migraine Forecast System"
date: 2025-12-06
description: "Established the core product analytics framework and architected a physician-guided forecasting for PeachyDay, boosting user engagement by 12%."
tags: ["Product Analytics", "Machine Learning", "Healthcare", "KPI Definition", "SQL"]
weight: 1
---

![Migraine Forecast Architecture](/images/migraine-forecast.png)

## 🍑 Project Context
**[PeachyDay](https://www.peachyday.co/)** is a digital health startup helping patients manage chronic migraines. As a Data Scientist, I bridged the gap between raw data and business strategy by defining the product metrics framework and building the core ML features.

## 🛠 Technical Challenges
1.  **Lack of Visibility**: The team had raw data but lacked defined KPIs to measure product health or feature success.
2.  **Clinical Validity**: A "black box" model is useless in healthcare; predictions must align with medical understanding.
3.  **User Retention**: Users lacked motivation to log data daily without immediate feedback.

## 💡 My Solutions

### 1. Product Analytics & Metrics Framework
I established the internal analytics system to track product health and user behavior.
* **KPI Definition**: Worked with stakeholders to define "North Star" metrics (e.g., DAU/MAU ratio, Feature Adoption Rate) and translated vague business questions into precise **SQL** queries.
* **Monitoring**: Built automated dashboards to track user interaction flows, helping the team identify drop-off points in the onboarding process.
* **Impact**: Transformed decision-making from intuition-based to data-driven, directly influencing the roadmap for the next 2 quarters.

<div align="center" style="margin: 20px 0;">
  <img src="/images/migraine-architecture.png" 
       alt="PeachyDay Architecture" 
       width="100%" 
       style="border-radius: 10px; box-shadow: 0 4px 20px rgba(0,0,0,0.1);">
  <p style="font-size: 0.9em; color: #666; margin-top: 10px;">
    <i>System Architecture with Physician-in-the-Loop</i>
  </p>
</div>

### 2. Physician-Guided Forecasting Engine
I developed an end-to-end prediction pipeline that translates clinical expertise into mathematical models.
* **Domain-Driven Feature Selection**: Collaborated with clinicians to identify medically relevant triggers (e.g., focusing on *barometric pressure changes*) and filter out noisy variables.
* **Clinical Calibration**: Applied post-processing techniques to smooth prediction curves based on doctors' advice, preventing false alarms and modeling the gradual onset of attacks.
* **Model Performance**: The final **Random Forest** model achieved an **18% accuracy boost** over the baseline.

### 3. "Migraine Wrapped" Data Product
To improve retention, I engineered a Spotify-Wrapped style data story for **1,000+ users**.
* **Visualization**: Showcased longitudinal behavioral trends (e.g., identifying personal habbits).
* **Impact**: This personalized feedback loop drove a **12% increase** in user engagement.

---

## 🚀 Key Results
* **Established** the company's first standardized Product Metrics Framework.
* **18%** Improvement in Forecast Accuracy via Clinical Feature Engineering.
* **12%** Uplift in User Engagement via Data Storytelling.

<div style="display: flex; gap: 20px; margin-top: 30px;">
  <a href="https://www.peachyday.co/" target="_blank" style="background-color: #ff6b6b; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px;">
    Visit PeachyDay Website
  </a>
</div>

> *Note: Code is proprietary. This page demonstrates the methodology, clinical collaboration, and business impact.*