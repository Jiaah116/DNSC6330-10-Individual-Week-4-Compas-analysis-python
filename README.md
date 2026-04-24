# DNSC6330-10-Individual-Week-4-COMPAS-Reliability-Audit-Python
# Week 4 Individual: Python Reliability & Robustness Audit (COMPAS)

## Course context
**Course:** DNSC 6330, Responsible Machine Learning (GW School of Business).

**This repo:** My Week 4 individual coding homework. It is the full reliability audit on the COMPAS pipeline we built in class (Lecture 4: drift, generalization, spurious patterns, robustness, slices).

Lecture PDFs are CC BY 4.0. If you fork or reuse, credit the instructor (name is on the slides).

## Overview
There is one Jupyter notebook. It starts from the ProPublica-style COMPAS replication, then adds sklearn models, LIME, SHAP, DiCE, some Solas-style disparity tables, and the Lecture 4 part (PSI, KS, MMD, stress on priors, slice metrics, etc.). I kept outputs in the file and added markdown so the grader can see what the numbers mean, not just the tables.

## How this matches the Week 4 assignment (Lecture 4)
Lecture 4 calls it a "Python coding audit." Rough map:

| Part | Homework (short version) | In the notebook |
|------|--------------------------|-----------------|
| **A** | Drift: PSI, KS, MMD; train vs test score | Lecture 4 live coding: drift, MMD in encoded space |
| **B** | Generalization: AUC, accuracy, log loss; gaps | Same block: train vs test tables |
| **C** | Spurious / counterfactual style checks | Lectures 2 and 4: permutation, stress, sensitivity |
| **D** | Robustness: stress `priors_count`, ICE, sensitivity | Lecture 4 |
| **E** | Slices: race, sex, age as applicable | Lectures 2 through 4, subgroup tables |

Lecture 4 grading stress: you need to explain results, not only print metrics.

## Why I did this
I recreated the COMPAS risk score work in Python, then checked whether the story still holds if you look at train/test split, drift, stress tests, and subgroups. A model can look fine overall and still do badly for a group or under a small data shift, so the writeup tries to say what each metric is for and what it is not.

## File to grade
`Week 4 individual assignment Yukari.T.ipynb`  
Before you submit, restart the kernel and run all cells once so everything runs clean top to bottom.

## Python libraries
**Core:** `pandas`, `numpy`, `statsmodels`, `matplotlib`, `scikit-learn`, `scipy`

**Extra (may need `pip install` once):** `lime`, `shap`, `dice-ml`

**Optional:** `solas-disparity` or `solas_ai` (notebook has a try/except; if it fails, use the pip line in the notebook or ask the prof about the class environment)

If a fresh install complains, open the first import block in each big section. That is what I actually used.

## How to run it
1. Clone the repo or download the `.ipynb`.
2. Open in Jupyter or Colab.
3. Run all. Fix any missing package with the `!pip` line in the notebook, then re-run.
4. Data loads from ProPublica’s `compas-scores-two-years.csv` over HTTPS (the raw `raw.githubusercontent.com` URL in the first data cell, not the GitHub web preview link).

**Submission (from Homework 1 / Lecture 1):** public GitHub, README, notebook. Email the repo link to the instructor. We used s.akinwumi@gwu.edu in the slides; check Canvas if that changed. They grade completeness, code quality, and whether you document and interpret, not just output.

## Author
Yukari Teranishi

## Due date
Lecture 4 slide OCR had **11:59 p.m. ET, April 30, 2026** for the individual coding audit. **Double-check on Canvas** in case it moved.

If you still have my old Week 1 README in git history, that was the R to Python copy; this README is only for the Week 4 hand-in.
