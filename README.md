# Capstone Project – Data Classification & Summarization (Breast Cancer)

**Date:** 2025-08-25

## Project Overview
Binary classification to predict **benign vs malignant** tumors using the public **Breast Cancer Wisconsin (Diagnostic)** dataset. I compare **Logistic Regression** and **Random Forest** and evaluate with Accuracy, Precision, Recall, F1, and ROC AUC.

## Raw Dataset
- Built-in public dataset from `sklearn.datasets.load_breast_cancer` (original from UCI ML Repository).
Link: https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29 or https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data
- Full raw CSV exported in this repo: `raw_breast_cancer_wisconsin.csv`.

## Analysis Process
1. Load dataset; target: `diagnosis` (0=malignant, 1=benign).
2. Train/test split (stratified).
3. Models: Logistic Regression (with scaling) and Random Forest.
4. Evaluate on test set; visualize ROC and confusion matrix; show feature importances.

## Insight & Findings
- The **best model**: Logistic Regression with ROC AUC = 0.995.
- Most important features (RF) include mean texture, mean concavity, worst area/perimeter/concavity, etc.
- Very strong separability suggests simple linear models perform well; tree models capture non-linearities.

## Conclusion & Recommendations
- Use **Random Forest** (or tuned Logistic Regression) for production; both perform strongly.
- Calibrate decision threshold to minimize false negatives (malignant classified as benign).
- Consider model calibration, hyperparameter tuning, and external validation.

## AI Support Explanation
- **LLM Summarization**: An LLM was used to synthesize insights & recommendations from metrics.
- **IBM Granite (Optional/Extension)**: The same summarization/classification workflows can be run on **watsonx.ai** with **Granite** models (see links in the slide deck).

## Artifacts
- Notebook: `breast_cancer_capstone.ipynb`
- Metrics: `metrics.json`
- Visuals: `roc_curve.png`, `confusion_matrix.png`, `feature_importances.png`
- Data: `raw_breast_cancer_wisconsin.csv`
