# Phase 3 Project: Predicting H1N1 Vaccination Status

## Project Overview
The goal of this project is to **predict whether an individual received the H1N1 flu vaccine** using demographic information, health behaviors, and opinions on vaccine effectiveness and risk.  

Understanding these patterns can help public health officials, healthcare providers, and pharmaceutical companies design better vaccination outreach and resource allocation strategies.

---

## Dataset
- Source: National 2009 H1N1 Flu Survey (USA)  
- Contains: demographic info, social and health behaviors, opinions on risk and vaccine effectiveness, vaccination status for H1N1 and seasonal flu.

---

## Approach

### 1. Data Understanding & Cleaning
- Explored vaccination patterns across demographics, behaviors, and opinions.  
- Visualized relationships using bar plots, heatmaps, and interaction charts.  
- Cleaned data by dropping columns with high missingness and irrelevant features (`respondent_id`, `seasonal_vaccine`).  

### 2. Preprocessing
- Imputed missing values for categorical and numerical features.  
- Standardized numerical features and one-hot encoded categorical variables.  
- Addressed class imbalance using SMOTE.  

### 3. Modeling
- **Logistic Regression:** Base and hyperparameter-tuned models.  
- **Decision Tree:** Base and tuned models.  
- Evaluated using ROC-AUC, accuracy, precision, recall, F1-score, confusion matrices, and ROC curves.

---

## Evaluation
| Model | Accuracy | ROC-AUC | Precision | Recall | F1-Score |
|-------|---------|---------|-----------|--------|-----------|
| Base Logistic Regression | 0.80 | 0.827 | 0.56 | 0.60 | 0.57 |
| Tuned Logistic Regression | 0.80 | 0.829 | 0.56 | 0.60 | 0.57 |
| Base Decision Tree | 0.79 | 0.801 | 0.55 | 0.57 | 0.56 |
| Tuned Decision Tree | 0.81 | 0.802 | 0.57 | 0.60 | 0.58 |

- Logistic Regression chosen as the final model due to higher ROC-AUC, indicating better discrimination between vaccinated and non-vaccinated individuals.  

---

## Key Findings
- **Doctor recommendation** is the strongest driver of vaccination.  
- **Belief in vaccine effectiveness** strongly increases uptake.  
- Individuals with **higher perceived risk** are more likely to vaccinate.  
- **Employment characteristics** influence vaccination behavior.  
- **Demographics** such as age (45–54) and race (Black respondents) slightly reduce likelihood of vaccination.

---

## Recommendations
1. **Leverage healthcare providers**
   - Encourage doctors to actively recommend vaccines.
2. **Increase risk awareness campaigns**
   - Communicate the likelihood and severity of infection.
3. **Promote vaccine effectiveness**
   - Address misinformation and reinforce public confidence.
4. **Targeted outreach**
   - Engage specific communities to understand barriers and improve access.

---

## Tools & Libraries
- Python, Pandas, NumPy, Matplotlib, Seaborn  
- Scikit-learn, Imbalanced-learn (SMOTE)  
- GridSearchCV for hyperparameter tuning
