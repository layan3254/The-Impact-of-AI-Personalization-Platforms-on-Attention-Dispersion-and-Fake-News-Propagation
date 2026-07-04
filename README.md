# Quantifying the Impact of AI Personalization Platforms on Attention Dispersion and Fake News Propagation

An end-to-end data analytics and predictive modeling project exploring how AI-driven recommendation loops on platforms like TikTok and Instagram Reels impact human attention spans, trap users in digital echo chambers, and accelerate the spread of misinformation.

---

## 👥 Project Team & Governance

### Prepared by:
*   **Lamyaa Aljohani**
*   **Layan Al-Muhammadi**
*   **Samar Asiri**
*   **Mohammad Alghifari**
*   **Bayan Bakehil**
*   **Rafeef Abdulaziz**
*   **Radhia Adam**

### Supervised by:
*   **Instructor:** Amasi Ibrahim
*   **Bootcamp:** Nywtk Bootcamp (Data Analytics using Python)
*   **Partnership:** In Collaboration with the Saudi Digital Academy (SDA) & The Hub
*   **Year:** 2026

---

## 📌 Table of Contents
1. [Introduction & Problem Statement](#1-introduction--problem-statement)
2. [Project Objectives](#2-project-objectives)
3. [Dataset Overview & Sources](#3-dataset-overview--sources)
4. [Methodological Workflow (7 Phases)](#4-methodological-workflow-the-7-phases)
5. [Tech Stack](#5-tech-stack)

---

## 1. Introduction & Problem Statement

### Introduction
The rapid growth of AI-driven recommendation systems on short-form video platforms (such as TikTok and Instagram Reels) has transformed digital content consumption by creating highly personalized, continuous engagement[cite: 1]. While enhancing user interaction, these technologies raise concerns regarding reduced attention spans, cognitive distraction, and the accelerated propagation of misinformation[cite: 1].

### Problem Statement
AI recommendation algorithms maximize engagement through continuous content loops that risk degrading human attention spans. Furthermore, personalized filtering traps users in informational "echo chambers," diminishing their capacity for critical evaluation and increasing vulnerability to fake news propagation[cite: 1].

---

## 2. Project Objectives
*   **Quantify** the relationship between AI recommendation engagement and user attention spans[cite: 1].
*   **Evaluate** how personalized content streams influence a user's capacity to distinguish credible from fake news[cite: 1].
*   **Extract** statistical insights to inform the design of responsible digital consumption behaviors[cite: 1].
*   **Deploy** an interactive platform allowing stakeholders to dynamically monitor these behavioral risks[cite: 1].

---

## 3. Dataset Overview & Sources

To evaluate digital behavior against content credibility, the project integrates three distinct datasets containing over **1 million records** post-processing[cite: 1]:

1.  **AI Recommendation Impact Dataset (`ai_recommendation_impact.csv`):** 
    Captures user demographic indicators, daily screen time, and digital distraction metrics[cite: 1].
    *   *Source:* [Kaggle Social Media Addiction & Mental Health Dataset](https://www.kaggle.com/datasets/abdulmaliklodhra/social-media-addiction-and-mental-health-dataset)
2.  **Misinformation Dataset (`gossipcop_fake.csv`):** 
    Contains verified unreliable articles from the *FakeNewsNet (GossipCop)* framework[cite: 1].
    *   *Source:* [Awesome Fake News Datasets Repository](https://github.com/thcheung/awesome-fake-news-datasets)
3.  **Credible News Dataset (`gossipcop_real.csv`):** 
    Serves as an authentic baseline control group for comparative analysis[cite: 1].
    *   *Source:* [Awesome Fake News Datasets Repository](https://github.com/thcheung/awesome-fake-news-datasets)

---

## 4. Methodological Workflow (The 7 Phases)

### 📈 Phase 1: Data Exploration & Quality Check
*   Analyzed dataset structures, shape, and features to ensure compatibility[cite: 1].
*   Assessed key data fields and verified behavioral indicators like attention scores and screen time distributions[cite: 1].

### 🧼 Phase 2: Data Cleaning
*   Programmatically dropped duplicate entries using `drop_duplicates()` to maintain statistical independence[cite: 1].
*   Handled missing values (`dropna()`), stripped text inconsistencies, and normalized platform URLs and gender records[cite: 1].

### 🛠️ Phase 3: Feature Engineering & Merging
*   **Label Creation:** Formulated the binary target column `is_fake` (0 for authentic news, 1 for fake news)[cite: 1].
*   **Platform Extraction:** Constructed a custom URL-parsing pipeline to extract distinct social media hosting platforms[cite: 1].
*   **Horizontal Join:** Conducted a comprehensive `Inner Join` mapping individual user behaviors to articles via shared platform vectors, generating a consolidated corpus of **1,196,067 records**[cite: 1].

### 📊 Phase 4: Exploratory Data Analysis (EDA)
*   Discovered an overall baseline rumor propagation rate of **14.19%** across the merged corpus[cite: 1].
*   Identified **Instagram** as the platform exhibiting the highest fake news density (**15.94%**)[cite: 1].
*   Mapped strong statistical linkages between highly emotional personalized feeds and spikes in digital addiction indicators[cite: 1].

### 🌲 Phase 5: Predictive Analytics — Decision Tree Architecture
*   Trained a base `DecisionTreeClassifier` pipeline to predict misinformation delivery[cite: 1].
*   *Performance Diagnostic:* The initial iteration yielded a perfect but flawed accuracy of 100%. The team diagnosed this as **Data Leakage** caused by identifier variables embedded during the join process[cite: 1]. The architecture was successfully refactored to eliminate tracking bias[cite: 1].

### 🌳 Phase 6: Predictive Analytics — Random Forest Architecture
*   Upgraded to an ensemble `RandomForestClassifier` (10 parallel estimators) to combat variance and overfitting[cite: 1].
*   Achieved a highly stable and generalized testing accuracy of **86.37%**[cite: 1]. 
*   Identified class imbalance challenges within the underlying data distribution and outlined future optimization using SMOTE[cite: 1].

### 🖥️ Phase 7: Interactive Deployment — Streamlit Architecture
*   Engineered a responsive dashboard application leveraging **Streamlit** and **Plotly**[cite: 1].
*   Includes dynamic user filtering across age groups, platforms, and risk metrics[cite: 1].
*   Features a dedicated **Platform Comparison Tool** displaying interactive side-by-side behavioral profiles[cite: 1].
*   The Link: https://ai-algorithms-attention-fake-news-dnayndd8sq4ndwtxbe82om.streamlit.app/

---

## 🛠️ Tech Stack
*   **Language:** Python
*   **Core Libraries:** Pandas, NumPy, Scikit-learn
*   **Visualization:** Plotly, Matplotlib, Seaborn
*   **Deployment:** Streamlit
*   **Environment:** Google Colab / Git
