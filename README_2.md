# Heart Disease ML Basics – Week 1

## Project Overview
This project is part of the BioAI Mastery – Month 1: Core ML + Biomedical Data Foundations.  
**Goal:** Build a foundational ML workflow using the Kaggle Heart Disease dataset, applying logistic regression and decision tree models, and document the workflow professionally.

### Key Objectives
- Load and explore biomedical dataset  
- Train classical ML models  
- Evaluate and visualize model performance  
- Identify key patient features driving predictions  

---

## Dataset
- **Source:** Kaggle Heart Disease Dataset  
- **Rows:** 1025 patients  
- **Columns:** 14 features including demographic, clinical, and exercise test results  

| Feature | Description |
|---------|-------------|
| age     | Patient age in years |
| sex     | 1 = male, 0 = female |
| cp      | Chest pain type (0=typical, 1=atypical, 2=non-anginal, 3=asymptomatic) |
| trestbps| Resting blood pressure (mm Hg) |
| chol    | Serum cholesterol (mg/dl) |
| fbs     | Fasting blood sugar > 120 mg/dl (1 = true, 0 = false) |
| restecg | Resting ECG results (0=normal, 1=ST-T abnormality, 2=LV hypertrophy) |
| thalach | Maximum heart rate achieved |
| exang   | Exercise-induced angina (1 = yes, 0 = no) |
| oldpeak | ST depression induced by exercise relative to rest |
| slope   | Slope of peak exercise ST segment (0=upsloping, 1=flat, 2=downsloping) |
| ca      | Number of major vessels colored by fluoroscopy (0–4) |
| thal    | Thalassemia type (3=normal, 6=fixed defect, 7=reversible defect) |
| target  | Heart disease diagnosis (1 = disease, 0 = no disease) |

---

## Data Exploration
- No missing values in the dataset  
- Visualizations: correlation heatmap, pairplots, ROC curves  
- Key observations: `cp`, `thal`, `oldpeak` are strongly correlated with heart disease  

---

## Models Trained
1. **Logistic Regression**  
   - Linear model  
   - Interpretable coefficients indicating how each feature affects disease probability  

2. **Decision Tree Classifier**  
   - Non-linear, flowchart-like model  
   - Captures complex interactions between features  
   - Feature importance extracted for interpretation  

---

## Evaluation Metrics

| Model | Accuracy | Precision | Recall | AUC |
|-------|----------|-----------|--------|-----|
| Logistic Regression | 79.5% | 75.6% | 87.4% | 0.88 |
| Decision Tree       | 98.5% | 100%  | 97.1% | 0.99 |

- **Interpretation:**  
  - TP = True Positive, TN = True Negative, FP = False Positive, FN = False Negative  
  - Decision tree outperforms logistic regression in all metrics  

---

## Feature Importance
- Decision Tree ranking: `cp > thal > ca > chol > oldpeak > age > thalach > trestbps > slope > sex > exang > restecg > fbs`  
- Logistic Regression coefficients indicate how each feature increases or decreases disease probability  
- Visualizations confirm `cp` (chest pain type) as the strongest predictor  

---

## Folder Structure
- `scripts/` → Python scripts for ML workflow  
- `Visualizations/` → Plots used in analysis and report  
- `datasets/` → Heart disease CSV  
- `models/` → Saved ML models (`.pkl` files)  
- `README.md` → Project summary and explanation  

---

## Next Steps
- Apply more advanced models (Random Forests, Gradient Boosting, SVM)  
- Explore neural networks for imaging or sequence-based biomedical datasets  
- Expand visualizations and explanations for clinical interpretability
