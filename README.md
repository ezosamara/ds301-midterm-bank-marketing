# DS 301 Midterm — Bank Marketing (UCI)

## Team
- Moataz Samara  


## Research Paper

Moro, S., Cortez, P., & Rita, P. (2014).  
**A Data-Driven Approach to Predict the Success of Bank Telemarketing.**  
*Decision Support Systems, 62, 22–31.*  

Intro dataset link (UCI Bank Marketing):  
https://archive.ics.uci.edu/dataset/222/bank+marketing

---

## Problem

We build classification models to predict **whether a bank client will subscribe to a term deposit** (`y = yes/no`) *before* making a telemarketing call.

This supports marketing by:
- Prioritizing the most promising clients
- Reducing the number of unnecessary calls
- Increasing campaign efficiency

---

## Dataset

- **Source:** UCI Machine Learning Repository — Bank Marketing dataset (`bank-full.csv`)
- **File in this repo:** `data/bank-full.csv`
- **Instances:** 45,211
- **Input features:** 16 (after dropping `duration`)
- **Target:** `y` (has the client subscribed a term deposit? `yes` / `no`)

We drop the feature **`duration`** because it is only known *after* the call ends, and using it would cause target leakage.

---

## Methods

We implement and compare two models that are also used in the original paper and covered in class:

1. **Logistic Regression**
   - With `class_weight="balanced"` to handle class imbalance
   - Interpretable coefficients
   - Outputs probabilities

2. **Decision Tree**
   - With `class_weight="balanced"`
   - Non-linear decision rules, easy to explain

### Preprocessing

- `StandardScaler` for numeric features
- `OneHotEncoder(handle_unknown="ignore")` for categorical features
- Combined via `ColumnTransformer` and used inside a `Pipeline`

### Evaluation

- Train/test split: **70% train, 30% test**, **stratified** on `y`
- Metrics:
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - **ROC-AUC** (main comparison metric)
- Plots:
  - Confusion matrices
  - ROC curves
  - Optional **Lift curve** (cumulative response) for marketing interpretation

We partially reproduce the original paper by:
- Using the same type of problem and dataset
- Dropping `duration`
- Evaluating with ROC-AUC and Lift

We **do not** implement Neural Networks and SVM in this project; they are discussed in the paper and mentioned as **future work**.

---

## Repository Structure

```text
.
├── README.md
├── data/
│   └── bank-full.csv
├── models/
│   └── DS301_BankMarketing_Midterm_Moataz_Samantha.ipynb
└── presentation/
    └── DS301_BankMarketing_Midterm_Moataz_Samantha.pptx   (or .pdf)
