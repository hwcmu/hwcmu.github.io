---
title: "Multimodal AI for ER Resource Prediction"
date: 2025-12-09
description: "Developed a hybrid predictive model fusing structured clinical data with NLP analysis of patient narratives to optimize IV fluid utilization in Emergency Departments."
tags: ["NLP", "Machine Learning", "Healthcare", "Gradient Boosting", "Multimodal"]
weight: 2
---

<div align="center" style="background-color: #0f172a; padding: 25px; border-radius: 15px; margin-bottom: 30px; box-shadow: 0 4px 20px rgba(0,0,0,0.3);">
  <img src="/images/iv-fluid-architecture.svg" alt="Multimodal Architecture Diagram" width="100%" style="border-radius: 8px;">
</div>

## 🎯 Project Overview
In Emergency Departments (ED), accurate prediction of resource utilization (like IV fluids) is critical for operational efficiency. Traditional models often ignore the rich information hidden in **unstructured patient narratives** (Chief Complaints). 

This project aimed to bridge this gap by developing a **Multimodal Machine Learning pipeline** that integrates structured clinical variables with NLP-derived text features.

## 🛠 Methodology

### Data Source
* Analyzed **13,115 patient records** from the National Hospital Ambulatory Medical Care Survey (NHAMCS-ED).
* **Input**: Mixed data types including demographics (structured) and triage notes (unstructured).

### The "Early Fusion" Strategy
I implemented an Early Fusion approach to combine distinct data modalities:
1.  **Structured Pipeline**: Processed clinical variables (vitals, age, history).
2.  **NLP Pipeline**: Experimented with three techniques to vectorize patient text:
    * *Baseline*: CountVectorizer (Bag-of-Words).
    * *Static Embeddings*: Word2Vec.
    * *Transformer*: Pre-trained **GPT-2** embeddings.
3.  **Modeling**: Concatenated features were fed into **Logistic Regression** and **Gradient Boosting Classifiers (GBC)**.

## 💡 Key Technical Insight
**"Simpler can be better."** Contrary to the popular trend of using Large Language Models (LLMs) for everything, my comparative analysis revealed a crucial insight:

> **CountVectorizer outperformed GPT-2** for this specific use case (AUC 0.786 vs 0.772).

**Why?** Emergency department narratives are typically **short, telegraphic, and keyword-driven** (e.g., "chest pain", "nausea"). They lack the complex semantic structures that Transformers like GPT-2 excel at capturing. Frequency-based methods (CountVectorizer) proved more effective at extracting these direct predictive signals without the noise of deep semantic layers.

## 🚀 Results & Impact
* **Performance**: The integrated GBC model (Structured + NLP) achieved the highest **AUC of 0.786**, significantly outperforming models using structured data alone.
* **Clinical Value**: Demonstrated that integrating free-text narratives provides a robust framework for improving clinical decision-making and resource allocation in the ED.

---

<div style="display: flex; gap: 15px; margin-top: 20px;">
  
  <a href="https://peerj.com/articles/cs-3441/" target="_blank" style="background-color: #0284c7; color: white; padding: 10px 20px; text-decoration: none; border-radius: 5px;">
    📄 Read Publication
  </a>
</div>