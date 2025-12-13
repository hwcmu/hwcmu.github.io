---
title: "AI-Powered Migraine Forecast System"
date: 2025-12-06
description: "Established the core product analytics framework and architected a physician-guided forecasting for PeachyDay, boosting user engagement by 12%."
tags: ["Product Analytics", "Machine Learning", "Healthcare", "KPI Definition", "SQL"]
weight: 1
---

![Migraine Forecast Architecture](/images/migraine-forecast.png)

## 🍑 Project Context
**[PeachyDay](https://peachyday.com)** is a digital health startup helping patients manage chronic migraines. As a Data Scientist, I bridged the gap between raw data and business strategy by defining the product metrics framework and building the core ML features.

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

### 2. Physician-Guided Forecasting Engine
I developed an end-to-end prediction pipeline that translates clinical expertise into mathematical models.
* **Domain-Driven Feature Selection**: Collaborated with clinicians to identify medically relevant triggers (e.g., focusing on *barometric pressure changes*) and filter out noisy variables.
* **Clinical Calibration**: Applied post-processing techniques to smooth prediction curves based on doctors' advice, preventing false alarms and modeling the gradual onset of attacks.
* **Model Performance**: The final **Random Forest** model achieved an **18% accuracy boost** over the baseline.

<div class="mermaid" align="center" style="background-color: #1a3c2b; padding: 30px; border-radius: 20px;">
graph LR
    classDef input fill:#dcedc8,stroke:#33691e,stroke-width:2px,color:#33691e
    classDef doctor fill:#ffccbc,stroke:#ff5722,stroke-width:3px,stroke-dasharray: 7 5,color:#bf360c,font-weight:bold
    classDef process fill:#fff9c4,stroke:#ff8a65,stroke-width:2px,color:#bf360c
    classDef output fill:#ff7043,stroke:#d84315,stroke-width:4px,color:#ffffff,font-weight:bold,font-size:1.1em

    subgraph Data["DATA INGESTION"]
        A("📱 User Logs"):::input
        B("☁️ NOAA Weather"):::input
    end

    subgraph Engine["CORE INTELLIGENCE"]
        Doc("👨‍⚕️ Neurologists<br/>(Clinical Guidance)"):::doctor
        ETL{"⚙️ ETL & <br/>Feature Selection"}:::process
        Model("🤖 Random Forest<br/>Model"):::process
    end

    Result(["✅ Risk Score<br/>(Curve Smoothed)"]):::output

    A ==> ETL
    B ==> ETL
    ETL ==> Model
    Model ==> Result

    Doc -.-> ETL
    Doc -.-> Result

    linkStyle 0,1,4,5 stroke:#fff9c4,stroke-width:3px
    linkStyle 2,3 stroke:#ff8a65,stroke-width:3px,stroke-dasharray: 7 5
    
    style Data fill:none,stroke:none,color:#dcedc8
    style Engine fill:none,stroke:none,color:#dcedc8
</div>

<script type="module">
    import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid/dist/mermaid.esm.min.mjs';
    mermaid.initialize({ startOnLoad: true, theme: 'base' });
</script>



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
  <a href="https://peachyday.com" target="_blank" style="background-color: #ff6b6b; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px;">
    Visit PeachyDay Website
  </a>
</div>

> *Note: Code is proprietary. This page demonstrates the methodology, clinical collaboration, and business impact.*