# ML-Based Network Intrusion Classification in IoT Environments Using the CICIoT2023 Dataset

**Course:** IT9201 — Machine Learning and Data Mining
**Programme:** MSc Artificial Intelligence (ICT9010), Bahrain Polytechnic
**Student:** Enas Alsawaeer — ID 12011215
**Lecturer:** Dr. Shomona Gracia Jacob
**Submission date:** 27 May 2026

---

## 1. Overview

This project builds and evaluates a machine learning pipeline that classifies CICIoT2023
network traffic at two levels: **binary** (Benign vs. Attack) and **multiclass**
(ten classes — Benign plus nine attack families: DDoS, DoS, Mirai, Recon, Spoofing,
WebAttack, BruteForce, Malware, Uploading). Four classifiers (Logistic Regression,
Random Forest, XGBoost, LightGBM) are compared under identical preprocessing and
evaluation conditions, with SMOTE for imbalance handling and Macro F1 as the primary
metric. The work is extended with SHAP explainability, edge-deployment benchmarking,
and a migration to the MindSpore framework plus a Deep Q-Network (DQN) baseline.

## 2. Contents of this submission

| File | Description |
|---|---|
| `[notebook_name].ipynb` | Full implementation (data loading, EDA, preprocessing, feature selection, modelling, tuning, evaluation, SHAP, benchmarking, MindSpore MLP, DQN) |
| `[report_name].pdf` | Project report |
| `Assessment_Cover_Sheet.docx` (or .pdf) | Completed assessment cover sheet |
| `CICIoT2023_sample.csv` | Representative stratified sample of the dataset (all ten classes) |
| `[saved_model].joblib` | Saved best model (tuned XGBoost) |
| `README.md` | This file |

## 3. Dataset

- **Full dataset:** CICIoT2023 — approximately 46.7 million flow records, 39 numerical
  features, generated from a real testbed of 105 IoT devices.
- **Official source (full dataset):** Canadian Institute for Cybersecurity (CIC),
  University of New Brunswick — https://www.unb.ca/cic/datasets/iotdataset-2023.html
  (access requires completing the short download form on that page).
- **Reference:** E. C. P. Neto et al., "CICIoT2023: A Real-Time Dataset and Benchmark
  for Large-Scale Attacks in IoT Environment," *Sensors*, 23(13), 5941, 2023.
  doi: 10.3390/s23135941
- **Sample provided:** Due to the size of the full corpus, a representative stratified
  sample (`CICIoT2023_sample.csv`) is included so the notebook can be run end-to-end
  without the full download.

## 4. Environment and dependencies

- Python (Anaconda distribution), Jupyter Notebook
- Local machine, 32 GB RAM
- A single fixed random seed (`RANDOM_STATE = 42`) is used throughout for reproducibility.

Main libraries:

```
numpy, pandas, matplotlib, seaborn
scikit-learn
xgboost
lightgbm
imbalanced-learn        # SMOTE
shap                    # explainability
mindspore               # MLP migration
torch                   # DQN baseline
```

Install with:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost lightgbm imbalanced-learn shap mindspore torch
```

## 5. How to run

1. Open `Machine Learning-Based Network Intrusion Classification in IoT Environments Using the CICIoT2023 Dataset.ipynb` in Jupyter Notebook.
2. Set the dataset path at the top of the notebook. To use the included sample, point it
   at the relative path `./CICIoT2023_sample.csv` (replace the absolute local path used
   during development).
3. Run the cells in order from top to bottom. The notebook loads the data, performs EDA
   and preprocessing, trains and tunes the models, and produces all figures and metrics.

> Note: the full pipeline (on the complete dataset) is memory- and time-intensive.
> Running on the provided sample reproduces the workflow and outputs at a smaller scale.

## 6. Source code repository

GitHub: `https://github.com/Enasnayel/MLandDM.git`

(The repository contains the notebook and the dataset sample; the full dataset is
available from the official CIC link in Section 3.)
