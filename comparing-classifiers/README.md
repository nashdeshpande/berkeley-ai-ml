# Bank Marketing Classifier Comparison

This project compares the performance of several machine learning classifiers (KNN, Logistic Regression, Decision Tree, SVM) on the UCI Bank Marketing dataset. The goal is to identify which model best predicts whether a client will subscribe to a term deposit, with a focus on recall for the positive class (subscribers).

## Summary of Findings
- All models were evaluated using accuracy, precision, recall, F1-score, and ROC AUC.
- All models had high test accuracy (~87–89%), but this is likely misleading due to class imbalance (few positives).
- Precision: Logistic Regression had the best precision (0.51), but this is on a small number of positive predictions.
- Recall: All models had very low recall (Logistic Regression: 0.02, SVM: 0.01, Decision Tree: 0.07, KNN: 0.06), meaning most actual subscribers were missed.
- F1-score: All models had low F1-scores, reflecting poor balance between precision and recall.
- ROC AUC: Logistic Regression achieved the highest (0.66), indicating it ranks positives higher than negatives, but still not ideal.

- The models are not capturing the positive class well. High accuracy is due to the dominant negative class, but actual subscribers are rarely identified. Improving recall (finding more subscribers) may require sacrificing precision.
- Logistic Regression and SVM performed similarly with default settings; neither clearly outperformed the other in recall or F1-score for the positive class.
- The SVM model was not the best by default; claims of SVM superiority likely depend on advanced tuning.
- Threshold tuning and class weighting improved recall for Logistic Regression, but reduced precision.
- Further improvements could be made with advanced SVM tuning, resampling, or feature engineering.

## Project Structure
- `comparing-classifiers/prompt_III.ipynb`: Main Jupyter Notebook with code, results, and analysis.
- `README.md`: This file.

## How to Run
1. Open `comparing-classifiers/prompt_III.ipynb` in Jupyter or VS Code.
2. Follow the notebook cells for data loading, model training, evaluation, and analysis.

## Link to Notebook
[Open the Jupyter Notebook](prompt_III.ipynb)