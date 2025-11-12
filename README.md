# ds301-midterm-bank-marketing
# DS 301 Midterm — Bank Marketing (UCI)
**Student:** Moataz Samara

**Dataset:** UCI Bank Marketing — using `bank-additional-full.csv` (41,188 rows, 20 inputs).  
**Target:** `y` (term deposit subscribed: yes/no).  
**Note:** We drop `duration` to avoid target leakage (per UCI docs).

**Paper (for reproduction framing):** Moro, Cortez & Rita (2014), *Decision Support Systems*.

## How to run
Open the notebook in Google Colab and Run All. The code one-hot encodes categoricals, scales numerics, trains LR/KNN/DT with 5-fold CV (ROC-AUC), and plots ROC.

## Repo
- `data/bank-additional-full.csv`
- `notebooks/BankMarketing_Midterm_MoatazSamara.ipynb`
