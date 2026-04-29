# COMPAS Analysis
**DNSC 6330 – Responsible Machine Learning**  
George Washington University · Norhelia Emilia Echevarria Angeles
- ID Student: G22339326

**Individual Homework 5 – Coding: From Accuracy to Accountability: ML Security Audit**

## Purpose of the Analysis

This section extends the COMPAS live-coding notebook from Lecture 05 by implementing a full adversarial security audit of the recidivism risk scoring pipeline. The goal is to evaluate whether the logistic regression and gradient-boosted tree models are vulnerable to evasion attacks, training-time poisoning, and membership inference — and to identify governance-level mitigations grounded in the NIST AI 100-2e2023 framework (Vassilev et al., 2024).


## What this notebook does

- **Part 1 — PGD Evasion Audit:** Implements Projected Gradient Descent for LR (analytical gradient via `sign(coef_)`) and GBT (numerical gradient via finite differences); runs the attack across ε ∈ {0.25, 0.5, 1.0, 2.0}; reports FPR by race, AIR, and ΔFPR from baseline for each model and ε; identifies the ε at which AIR crosses 0.80; compares model vulnerability in a written analysis with model selection implications
- **Part 2 — Poisoning Loop with Fairness Monitoring:** Extends the label-flip poisoning loop from the lecture to target Caucasian defendants in addition to African-American; plots AUC degradation and AIR curves for both target-race variants on the same axes; identifies the stealth zone (|ΔAUC| ≤ 2pp while AIR exits [0.80, 1.25]); tests whether a PSI-based drift monitor (threshold < 0.10) would detect either attack, with empirical evidence from feature PSI and score PSI outputs
- **Part 3 — Membership Inference Depth:** Computes shadow-model MI AUC for both LR and GBT using the existing `meta_clf` from the lecture; plots confidence-gap histograms for both models side by side; tests the Yeom et al. (2018) hypothesis that generalization gap predicts MI AUC; runs an L2 regularization sweep (C ∈ {0.01, 0.1, 1.0, 10.0}) and plots MI AUC, Test AUC, and AIR vs. log₁₀(C)
- **Part 4 — Reflection:** Identifies the single highest-risk finding across all three parts; proposes one proactive and one reactive mitigation; quantifies each mitigation's effect using experimental results; discusses disparate impact of both mitigations on each racial group



## Libraries

- `pandas`
- `numpy`
- `matplotlib`
- `scikit-learn`
- `sklearn.metrics` (`roc_auc_score`, `roc_curve`, `RocCurveDisplay`, `confusion_matrix`)
- `sklearn.linear_model` (`LogisticRegression`)
- `sklearn.ensemble` (`GradientBoostingClassifier`)
- `sklearn.tree` (`DecisionTreeClassifier`)
- `sklearn.model_selection` (`StratifiedShuffleSplit`)
  
## Instructions for Reproducing the Results

1. Open [Google Colab](https://colab.research.google.com/)
2. Click **File → Upload notebook** and select `Homework05_Norhelia_Echevarria.ipynb`
3. Run all cells: **Runtime → Run all**

All required libraries are pre-installed in Colab. No additional setup needed.
Run all cells sequentially from top to bottom.

## Data Source

The dataset is fetched automatically at runtime, no manual download needed.
