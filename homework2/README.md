# COMPAS Analysis
**DNSC 6330 – Responsible Machine Learning**  
George Washington University · Norhelia Emilia Echevarria Angeles
- ID Student: G22339326

**Individual Homework 2 — Coding: Explaining the COMPAS Replacement Model**

## Purpose of the Analysis

This notebook extends the COMPAS recidivism analysis from Lecture 02 by training  a replacement model and applying three explainability methods: SHAP, LIME, and DiCE counterfactuals.

## What this notebook does

- Cleans and filters the COMPAS dataset  
- Explores demographic patterns (race, gender, age)  
- Builds a logistic regression model  
- Estimates relative risk across groups  
- Evaluates fairness using confusion matrices, FPR, and FNR
- Analyzes feature importance using SHAP (global explanations)
- Explains individual predictions using LIME (local explanations)
- Compares global vs. local interpretability (SHAP vs. LIME)
- Identifies potential proxy effects related to sensitive attributes (e.g., race)

## Libraries

- `pandas`  
- `numpy`
- `matplotlib` 
- `statsmodels`
- `shap`
- `lime`

## Instructions for Reproducing the Results

1. Open [Google Colab](https://colab.research.google.com/)
2. Click **File → Upload notebook** and select `Homework02_Norhelia_Echevarria.ipynb`
3. Run all cells: **Runtime → Run all**

All required libraries are pre-installed in Colab. No additional setup needed.
Run all cells sequentially from top to bottom.

## Data Source

The dataset is fetched automatically at runtime, no manual download needed:
https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv
