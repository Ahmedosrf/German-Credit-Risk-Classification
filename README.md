# German Credit Risk Classification

[![Dataset](https://img.shields.io/badge/dataset-UCI%20German%20Credit-0F766E)](https://archive.ics.uci.edu/dataset/144/statlog+german+credit+data)
[![scikit--learn](https://img.shields.io/badge/library-scikit--learn-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Notebook](https://img.shields.io/badge/interface-Jupyter-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Status](https://img.shields.io/badge/status-educational%20experiment-blue)](#limitations)

> A notebook-based comparison of classical machine-learning classifiers on the UCI Statlog German Credit dataset.

## Overview

This project explores binary credit-risk classification using a collection of scikit-learn models. It includes data visualization, preprocessing, model comparison, hyperparameter experimentation, and cross-validation analysis. The work is intended for learning and research; it is not a production lending model or a substitute for human review.

## Models Compared

The notebooks evaluate several ensemble and non-ensemble methods:

| Model | Role |
|---|---|
| Support Vector Classifier | Non-linear margin-based classifier. |
| Gaussian Naive Bayes | Probabilistic baseline. |
| Random Forest | Bagged decision-tree ensemble. |
| Extra Trees | Randomized tree ensemble. |
| Gradient Boosting | Sequential boosting model. |
| AdaBoost | Adaptive boosting baseline. |
| Bagging | Bootstrap aggregation comparison. |

## Reported Cross-Validation Results

The original experiment identifies Gradient Boosting as the strongest model under its 10-fold cross-validation setup:

| Metric | Mean | Variation |
|---|---:|---:|
| Precision | 0.85 | ±0.17 |
| Recall | 0.86 | ±0.04 |
| ROC-AUC | 0.91 | ±0.09 |

These are **cross-validation estimates**, not a guarantee of performance on new applicants. Recompute them after changing preprocessing, splits, features, or library versions.

## Repository Contents

```text
.
├── germancredit.ipynb   # Exploration, preprocessing, and model search
├── Final_Model.ipynb     # Final model comparison and selected models
└── README.md
```

## Run the Notebooks

```bash
git clone https://github.com/Ahmedosrf/German-Credit-Risk-Classification.git
cd German-Credit-Risk-Classification
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\\Scripts\\activate
pip install jupyter pandas numpy matplotlib seaborn scikit-learn
jupyter notebook
```

Open `germancredit.ipynb` first, run the preprocessing and exploratory cells, then review `Final_Model.ipynb`. Save the exact dataset version, random seed, feature transformations, class mapping, and evaluation protocol with each experiment.

## Evaluation Guidance

Because credit labels can be imbalanced and consequential, report per-class precision, recall, F1-score, ROC-AUC, the confusion matrix, and probability calibration. A single aggregate accuracy number can hide poor performance for one group. Any extension intended for real decisions also requires subgroup fairness analysis, privacy review, explainability, and human oversight.

## Limitations

The dataset is historical and may encode social or economic biases. Its labels are not a universal definition of creditworthiness, and performance on it should not be generalized to Palestinian or other populations without local validation. Do not use the notebooks to approve, reject, rank, or price real credit applications.

## Maintainer

[Ahmed Osrof](https://github.com/Ahmedosrf)
