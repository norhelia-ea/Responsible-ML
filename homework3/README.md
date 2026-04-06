# COMPAS Analysis
**DNSC 6330 – Responsible Machine Learning**  
George Washington University · Norhelia Emilia Echevarria Angeles
- ID Student: G22339326

**Individual Homework 3 – Coding: Disparate Impact Audit**

## Purpose of the Analysis

This section extends the COMPAS analysis by applying formal bias measurement techniques to the dataset and the replacement model built in Lecture 02. The goal is to quantify disparate impact across racial and gender groups using legally grounded metrics.

## What this notebook does

- Computes **Adverse Impact Ratio (AIR)** and **Marginal Effect (ME)** for race and sex using the solas-ai library and manual Python functions, confirming identical results across both methods
- Computes **Standardized Mean Difference (SMD)** on the COMPAS decile score
- Builds an **intersectional analysis** (race × sex) and identifies the worst-affected subgroup
- Computes **FPR and FNR disparities** by race and tests statistical significance using two-proportion z-tests
- Produces a **publication-quality grouped bar chart** of FPR and FNR by race with Caucasian as the reference group
- Writes a **compliance memo** summarizing findings, metrics used, and limitations addressed to a hypothetical regulato

## Libraries

- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`
- `solas-ai` (`solas_disparity`)
- `shap`
- `lime`
- `dice-ml`
- `scikit-learn`

## Instructions for Reproducing the Results

1. Open [Google Colab](https://colab.research.google.com/)
2. Click **File → Upload notebook** and select `Homework03_Norhelia_Echevarria.ipynb`
3. Run all cells: **Runtime → Run all**

All required libraries are pre-installed in Colab. No additional setup needed.
Run all cells sequentially from top to bottom.

## Data Source

The dataset is fetched automatically at runtime, no manual download needed.
