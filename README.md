# Breast Cancer Diagnostic Classification

A machine learning project classifying breast tumor biopsies as malignant or benign, built to apply and strengthen my Python and machine learning skills.

## Overview

This project uses the Breast Cancer Wisconsin (Diagnostic) dataset, a public dataset of 569 tumor biopsies, each described by 30 measurements taken from digitized images of cell nuclei (radius, texture, concavity, and related features). The goal is to predict whether a tumor is malignant or benign based on these measurements.

## Dataset

The dataset is loaded directly from scikit-learn (sklearn.datasets.load_breast_cancer), so no external download is required. It contains 569 samples: 212 malignant and 357 benign, with no missing values.

## Methods
Exploratory Data Analysis: examined class distribution and feature relationships. Tumor size (mean radius) showed a clear separation between malignant and benign cases, and a correlation heatmap identified which features were most strongly associated with malignancy.
Preprocessing: split the data into training (80%) and testing (20%) sets, stratified to preserve class balance. Features were standardized using StandardScaler so all measurements were on a comparable scale.
Modeling: trained and compared two classifiers:
Logistic Regression
Random Forest
Evaluation: assessed both models using accuracy, confusion matrices, and classification reports, with particular attention to recall on the malignant class, since missing an actual cancer case is a more costly error than a false alarm in this context.

## Results
| Model | Accuracy | Malignant Recall |
|---|---|---|
| Logistic Regression | 98.25% | 0.98 |
| Random Forest | 95.61% | 0.93 |

Logistic Regression outperformed Random Forest on this dataset, both in overall accuracy and in recall on the malignant class (missing only 1 of 42 malignant cases in the test set). This was a useful finding: with a relatively small, fairly separable dataset, the simpler and more interpretable model performed better than the more complex one, reinforcing that model choice should be driven by the data and the problem rather than by defaulting to the most sophisticated option available.

## Tools Used

Python, pandas, NumPy, matplotlib, seaborn, scikit-learn

## Next Steps

Possible extensions include hyperparameter tuning, testing additional models, and examining feature importance in more depth to understand which measurements drive predictions most strongly.
