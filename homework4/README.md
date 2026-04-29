# COMPAS Analysis
**DNSC 6330 – Responsible Machine Learning**  
George Washington University · Norhelia Emilia Echevarria Angeles
- ID Student: G22339326

**Individual Homework 4 – Coding: From Accuracy to Accountability: Stress Testing a Predictive Model**

## Purpose of the Analysis

This section extends the COMPAS live-coding notebook from Lecture 04 by implementing a full reliability audit of the recidivism risk scoring pipeline. The goal is to evaluate whether the logistic regression and gradient-boosted tree models remain reliable, fair, and generalizable beyond their training conditions — covering distribution drift, generalization failure, spurious correlations, robustness under stress, and subgroup performance disparities.


## What this notebook does

- **Part A — Distribution Drift:** Computes Population Stability Index (PSI) and Kolmogorov–Smirnov (KS) tests for all numeric features, calculates Maximum Mean Discrepancy (MMD²) in the encoded feature space, and compares train vs. test score distributions visually and statistically for both models
- **Part B — Generalization:** Compares train vs. test AUC, accuracy, and log loss for both LR and GBT; flags generalization gaps exceeding governance thresholds (AUC gap > 0.05, log loss gap > 0.10); produces side-by-side ROC curves with gap annotations
- **Part C — Spurious Correlation Probe:** Runs counterfactual swaps on `race_factor` (African-American ↔ Caucasian) and `gender_factor` (Male ↔ Female) directly in the feature matrix; measures mean Δp and its distribution for both models; flags cases where mean |Δp| > 0.05 for escalation to full fairness audit
- **Part D — Robustness:** Stress-tests `priors_count` across a scenario grid from 0 to 30; produces ICE curves for a random sample of 80 individuals; computes sensitivity index Vj for both models and interprets domain justification vs. spurious reliance
- **Part E — Slice-Based Evaluation:** Computes AUC, FPR, and FNR separately for every demographic subgroup defined by `race_factor`, `gender_factor`, and `age_factor`; produces grouped bar charts with aggregate reference lines; connects findings to the Impossibility Theorem


## Libraries

- `pandas`
- `numpy`
- `matplotlib`
- `scipy`
- `scikit-learn`
- `sklearn.metrics` (`roc_auc_score`, `accuracy_score`, `log_loss`, `roc_curve`, `confusion_matrix`)
- `sklearn.metrics.pairwise` (`rbf_kernel`)
  
## Instructions for Reproducing the Results

1. Open [Google Colab](https://colab.research.google.com/)
2. Click **File → Upload notebook** and select `Homework03_Norhelia_Echevarria.ipynb`
3. Run all cells: **Runtime → Run all**

All required libraries are pre-installed in Colab. No additional setup needed.
Run all cells sequentially from top to bottom.

## Data Source

The dataset is fetched automatically at runtime, no manual download needed.
