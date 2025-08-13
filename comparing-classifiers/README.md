# Bank Marketing Classifier Comparison

This project compares the performance of several machine learning classifiers (KNN, Logistic Regression, Decision Tree, SVM) on the UCI Bank Marketing dataset. The goal is to identify which model best predicts whether a client will subscribe to a term deposit, with a focus on recall for the positive class (subscribers).

## Summary of Findings
- All models were evaluated using accuracy, precision, recall, F1-score, and ROC AUC.
- All models had high test accuracy (~87–89%), but likely misleading because the dataset is imbalanced (few positives).
- Precision: Logistic Regression had the best precision, at 0.51, indicating it is correct about half the time. However, this is on a very small number of positive predictions.
- Recall: All models have very low recall (Logistic Regression: 0.02, SVM: 0.01, Decision Tree: 0.07, KNN: 0.06), indicating the models are missing most of the actual positive cases (term deposit subscribers). For example, Logistic Regression only finds 2% of the true positives.
- F1-score: All models have very low F1-scores, reflecting the poor balance between precision and recall.
- ROC AUC: Logistic Regression: 0.66 (best), indicating Logistic Regression is best at ranking positives higher than negatives, but still not great.

- These findings indicate that the models are not capturing the positive class well. They are accurate overall because the negative class dominates, but they rarely identify actual subscribers. To improve performance, it is important to find the right balance between precision and recall. If we assume the business goal is to find as many subscribers as possible (maximize recall), these models need improvement, at the cost of precision.
- Logistic Regression and SVM performed similarly with default settings, but neither clearly outperformed the other in recall or F1-score for the positive class in this notebook.
- The SVM model was not the best by default; the paper's claim that SVM is best is likely based on more advanced tuning and evaluation.
- Threshold tuning and class weighting improved recall for Logistic Regression, but at the cost of precision.
- Further improvements could be made by advanced SVM tuning, resampling, or feature engineering.

## Project Structure
- `module17_starter/prompt_III.ipynb`: Main Jupyter Notebook with all code, results, and analysis.
- `README.md`: This file.

## How to Run
1. Open `module17_starter/prompt_III.ipynb` in Jupyter or VS Code.
2. Follow the notebook cells for data loading, model training, evaluation, and analysis.

## Link to Notebook
[Open the Jupyter Notebook](module17_starter/prompt_III.ipynb)