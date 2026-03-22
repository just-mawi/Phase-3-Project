# Phase 3 Project: Predicting H1N1 Vaccination Status
**An Analysis of the 2009 National H1N1 Flu Survey**

## 1. Project Overview
This project utilizes machine learning to predict whether individuals received the H1N1 flu vaccine based on their social, economic, and demographic backgrounds, as well as their opinions on vaccine effectiveness and personal risk.

### Business Objective
By identifying the key drivers of vaccination, this project provides actionable insights for:
* **Public Health Strategy:** Designing outreach for future respiratory outbreaks.
* **Resource Allocation:** Identifying and supporting high-risk or low-uptake demographics.
* **Communication:** Addressing specific barriers like perceived risk and vaccine skepticism.

---

## 2. Data Understanding
The dataset originates from the **National 2009 H1N1 Flu Survey**. It contains approximately 26,000 responses with over 30 features.
* **Key Features:** Behavioral (mask-wearing, hand-washing), Opinions (perceived risk, vaccine effectiveness), and Demographics (age, race, income).
* **Target Variable:** `h1n1_vaccine` (Binary: 0 = No, 1 = Yes).
* **Class Imbalance:** Only ~21% of respondents received the vaccine, which was addressed using **SMOTE** during the modeling phase.

---

## 3. Methodology

### Data Preprocessing
* **Cleaning:** Dropped features with >50% missing values and removed irrelevant identifiers.
* **Pipeline:** Used `ColumnTransformer` to handle:
    * **Categorical Data:** Imputed with "most frequent" and encoded via `OneHotEncoder`.
    * **Numerical Data:** Imputed with "median" and scaled via `StandardScaler`.
* **Imbalance Handling:** Utilized **SMOTE** within an `ImbPipeline` to ensure fair class representation without data leakage.

### Modeling & Evaluation
**Logistic Regression** and **Decision Tree** models.
* **Primary Metric:** **ROC-AUC** (Area Under the Receiver Operating Characteristic Curve).
* **Secondary Metrics:** Accuracy, F1-Score, and Recall.

---

## 4. Performance Summary

| Model | Accuracy | ROC-AUC | F1-Score |
| :--- | :--- | :--- | :--- |
| **Tuned Logistic Regression** | 0.776 | **0.829** | 0.577 |
| Tuned Decision Tree | **0.810** | 0.813 | 0.547 |

**Final Model Choice:** **Logistic Regression (Tuned)**. While the Decision Tree had slightly higher accuracy, the Logistic Regression model provided superior class separation (ROC-AUC) and a higher F1-Score

---

## 5. Key Findings
* **Doctor Recommendations:** The single strongest predictor of vaccination.
* **Risk Perception:** A direct correlation exists between personal fear of the virus and vaccine uptake.
* **Vaccine Confidence:** Belief in vaccine effectiveness significantly outweighs demographic factors in predicting behavior.
* **Demographics:** Specific groups (e.g., ages 45-54 and Black respondents) showed slightly lower uptake, suggesting a need for culturally competent outreach.

---

## 6. Recommendations
1. **Empower Providers:** Encourage primary care physicians to issue direct, personal vaccine recommendations.
2. **Targeted Risk Communication:** Campaigns should focus on the specific severity and likelihood of infection.
3. **Build Transparency:** Combat misinformation by emphasizing the success and effectiveness of vaccines.
4. **Community Engagement:** Address systemic barriers by working with trusted community leaders in low-uptake demographics.
