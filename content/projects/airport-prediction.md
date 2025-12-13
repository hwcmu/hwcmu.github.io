---
title: "Real-Time Flight Delay Prediction"
date: 2025-12-13
# 这是一个简短的描述，会显示在首页列表里
description: "Predicts flight delays using 4M+ records and live NOAA weather via TabPy. Bridges ML & BI with real-time SHAP explanations."
# 标签要打准，方便检索
tags: ["Tableau", "Python", "Machine Learning", "TabPy", "API"]
weight: 10  # 数字越小，排得越靠前
---

![Dashboard Demo](/images/airport-dashboard-demo.png)

## 🚀 Project Overview
This project demonstrates an end-to-end flight delay prediction system. By integrating **Tableau** with **Python (TabPy)**, the system fetches live weather data from the **NOAA API** and runs a Logistic Regression model (trained on **4M+ records**) to predict delays in real-time.

### 🔑 Key Features
* **Hybrid Data Pipeline**: Merges historical rolling statistics with live API weather data.
* **Real-time Interaction**: Users select flight routes, and the model computes delay probabilities instantly.
* **Explainable AI**: Provides top-3 **SHAP** root cause explanations for every prediction.

---

## 📊 Visuals & Poster
Since Tableau Public does not support external Python scripts (TabPy), the interactive dashboard above utilizes a static dataset snapshot for demonstration.

<div style="display: flex; gap: 20px; flex-wrap: wrap;">

  <a href="https://github.com/hwcmu/Real-Time-Flight-Delay-Prediction-TabPy-Tableau-NOAA-Integration" target="_blank" style="background-color: #333; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px;">
    View Source Code on GitHub 
  </a>

  <a href="/docs/project-poster.pdf" target="_blank" style="background-color: #0055aa; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px;">
    Download Research Poster (PDF)
  </a>

</div>

---

## 🛠 Technical Architecture
* **Data Source**: Bureau of Transportation Statistics (BTS) & NOAA Weather API.
* **Model**: Logistic Regression (Scikit-learn) and SHAP, optimized for inference speed.
* **Integration**: TabPy server acting as the bridge between Tableau frontend and Python backend.