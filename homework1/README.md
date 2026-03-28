# COMPAS Analysis
**DNSC 6330 – Responsible Machine Learning**  
George Washington University · Norhelia Echevarria

**Individual Homework 1 - Translating an R Machine Learning Workflow into Python**

## Purpose of the Analysis

This notebook replicates and extends **ProPublica's investigation of the COMPAS recidivism algorithm** using Python. COMPAS (Correctional Offender Management Profiling for Alternative Sanctions) is a tool that predicts whether a defendant will reoffend within two years. ProPublica's 2016 analysis found evidence of **racial bias** in its predictions.

The workflow covers five analytical stages:

1. **Data loading and cleaning**: Fetching the COMPAS dataset and filtering out low-quality records (missing charge dates, invalid offense codes, insufficient follow-up time). Final sample: 6,172 defendants.
2. **Exploratory analysis**: Demographic breakdowns by race, gender, and age; decile score distributions across racial groups.
3. **Logistic regression modeling**: Predicting whether a defendant receives a high COMPAS score, controlling for criminal history, charge severity, and demographics.
4. **Relative risk estimation**: Quantifying how much more likely Black, female, and younger defendants are to receive higher risk scores.
5. **Fairness evaluation**: Overall and race-stratified confusion matrices; False Positive Rate (FPR) and False Negative Rate (FNR) disparity analysis.

## Python Libraries Used

| Library | Purpose |
|---|---|
| `pandas` | Data loading, filtering, manipulation, and crosstabs |
| `numpy` | Numerical operations and array handling |
| `matplotlib` | Decile score distribution plots by race |
| `statsmodels` | Logistic regression (`smf.logit`) and model interpretation |

---

## Instructions for Reproducing the Results

1. Open [Google Colab](https://colab.research.google.com/)
2. Click **File → Upload notebook** and select `Homework01_Norhelia_Echevarria.ipynb`
3. Run all cells: **Runtime → Run all**

All required libraries are pre-installed in Colab. No additional setup needed.

Run all cells sequentially from top to bottom.

### Data Source

The dataset is fetched automatically at runtime — no manual download needed:
```
https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv
```


## References

- Angwin et al. (2016). *Machine Bias*. ProPublica. https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing  
- ProPublica COMPAS Analysis: https://github.com/propublica/compas-analysis
