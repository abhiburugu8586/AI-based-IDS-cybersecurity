# AI-Based Intrusion Detection System for Cybersecurity

Hybrid machine learning IDS combining supervised classifiers (Decision Tree,
Random Forest, Gradient Boosting) with an Isolation Forest anomaly detector
to improve zero-day attack detection on CICIDS2017, with SHAP-based
explainability.

This repository contains the implementation for my MSc dissertation,
*"Design and Development of an AI-Based Intrusion Detection System for
Cybersecurity"* (Sheffield Hallam University).

## Overview

Traditional signature-based Intrusion Detection Systems (IDS) struggle to
detect zero-day attacks — attacks of a type not previously seen. This
project designs, implements and evaluates a hybrid machine-learning IDS
that combines a supervised classifier with an unsupervised anomaly
detector, and applies SHAP to interpret its predictions.

Two experimental strands are implemented:

1. **Multi-model supervised classification** — Decision Tree, Random Forest
   and Gradient Boosting trained on the full CICIDS2017 dataset, compared
   on accuracy, precision, recall, F1 and ROC-AUC, with SHAP explainability
   applied to the best model.
2. **Hybrid zero-day evaluation** — a supervised Random Forest combined
   with a benign-only Isolation Forest anomaly detector, tested against
   attack types entirely withheld from training to simulate genuine
   zero-day conditions.

## Key result

A purely supervised model's recall on genuinely unseen (zero-day) attacks
collapsed to **0.02%**, despite 99.8% accuracy on a conventional held-out
test split. Combining it with an unsupervised anomaly detector raised
zero-day recall roughly **160-fold to 3.90%**, at a measurable precision
cost on known traffic — empirically demonstrating why same-distribution
benchmark evaluation overstates real-world zero-day performance.

## Repository structure

```
notebooks/   Two Jupyter notebooks (see below)
figures/     Exported charts and confusion matrices used in the report
data/        Instructions for obtaining the CICIDS2017 dataset (not included)
```

## Notebooks

| Notebook | Description |
| --- | --- |
| `notebooks/IDS_For_cybersecurity.ipynb` | Data pre-processing, mutual-information feature selection, and training/comparison of Decision Tree, Random Forest and Gradient Boosting classifiers, with SHAP explainability. |
| `notebooks/Hybrid_zero_day_detection.ipynb` | Two-stage hybrid pipeline (Isolation Forest + Random Forest) evaluated against attack types withheld entirely from training. |

## How to run

1. Download the CICIDS2017 dataset — see `data/README.md` for instructions.
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```
3. Open the notebooks in Jupyter, JupyterLab, or Google Colab and run the
   cells in order. If using Colab, upload the CSVs to your Google Drive and
   update the file paths at the top of each notebook accordingly.

## Dataset

This project uses **CICIDS2017** (MachineLearningCSV release), produced by
the Canadian Institute for Cybersecurity, University of New Brunswick. See
`data/README.md` for the citation requirement and download link.



## Author

Abhishekar Burugu — MSc Computing, Sheffield Hallam
University. Supervisor: Konstantinos Domdouzis.
