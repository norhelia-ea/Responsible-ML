# COMPAS Analysis
**DNSC 6330 – Responsible Machine Learning**  
George Washington University · Norhelia Emilia Echevarria Angeles
ID Student: G22339326

**Individual Homework 1 - Translating an R Machine Learning Workflow into Python**

## Purpose of the Analysis

This notebook replicates and extends ProPublica's investigation of the COMPAS recidivism algorithm using Python. COMPAS (Correctional Offender Management Profiling for Alternative Sanctions) is a tool that predicts whether a defendant will reoffend within two years. ProPublica's 2016 analysis found evidence of racial bias in its predictions.

## What this notebook does

- Cleans and filters the COMPAS dataset  
- Explores demographic patterns (race, gender, age)  
- Builds a logistic regression model  
- Estimates relative risk across groups  
- Evaluates fairness using confusion matrices, FPR, and FNR  

## Libraries

- `pandas` – data processing  
- `numpy` – numerical operations  
- `matplotlib` – visualization  
- `statsmodels` – logistic regression  

## Instructions for Reproducing the Results

1. Open [Google Colab](https://colab.research.google.com/)
2. Click **File → Upload notebook** and select `Homework01_Norhelia_Echevarria.ipynb`
3. Run all cells: **Runtime → Run all**

All required libraries are pre-installed in Colab. No additional setup needed.
Run all cells sequentially from top to bottom.

### Data Source

The dataset is fetched automatically at runtime — no manual download needed:
https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv


