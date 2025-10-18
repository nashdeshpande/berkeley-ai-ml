### Bank Term Deposit Data Analysis for Subscription Prediction

**Nachiket Deshpande**

#### Executive summary
This project analyzes a Portuguese bank’s marketing campaign dataset to predict whether a client will subscribe to a term deposit. By leveraging machine learning models, the goal is to identify the most important factors influencing subscription and to provide actionable insights for improving campaign effectiveness.

#### Rationale
Understanding the drivers of customer subscription decisions can help banks optimize their marketing strategies, reduce costs, and improve customer targeting. Predicting term deposit subscription is particularly valuable because it aligns customer needs with bank offerings while minimizing wasted outreach.

#### Research Question
Can we predict whether a client will subscribe to a term deposit based on attributes such as age, job, marital status, account balance, and details of the marketing campaign?

#### Data Sources
I will be using the **Bank Marketing Dataset** from Kaggle: [Bank Marketing Dataset (Full)](https://www.kaggle.com/datasets/sushant097/bank-marketing-dataset-full), which contains over **40,000 client records** collected during marketing campaigns conducted by a Portuguese banking institution.

#### Methodology
I plan to apply supervised machine learning classification techniques such as logistic regression, random forest, and gradient boosting.  
Data preprocessing will include:  
- Handling missing values  
- Encoding categorical features (job, marital, education, etc.)  
- Scaling numerical features (age, balance, campaign duration)  
- Addressing class imbalance (resampling or class weights)

Models will be evaluated using accuracy, precision, recall, F1-score, and ROC-AUC. Feature importance analysis will also be used to interpret results.

#### Results
EDA results are as follows:
- **Dataset structure**: The dataset contains 45,211 entries with 17 features. No missing values were found, and no duplicate rows were detected.  
- **Class imbalance**: The dataset is imbalanced. A much smaller proportion of customers (12%) subscribed compared to those who did not (88%). This will require resampling or class-weight adjustments during modeling.
**Outliers**: Some extreme values were observed in numerical features, particularly in `balance` (very high account balances), `pdays` (values up to 999 indicating no previous contact), and `campaign` (clients contacted dozens of times). These may need treatment or capping before modeling.
- **Target variable relationships**: 
    - **Education and job**: Students (34%) and retirees (24%) seem to subscribe the most. Customers with higher education (tertiary) seem to subscribe more than other levels of education (16%).
    - **Campaign fatigue**: Subscription rates decline (from approx 18% to 5%) as the number of campaign contacts increases, consistent with customer fatigue. This is also seen in the correlation heatmap (-0.08 correlation between campaign and y)
    - **Duration**: Longer call durations are strongly associated with higher subscription likelihood — this may become a key driver in modeling. This shows up in the correlation heatmap with +0.52 between duration and y.
    - **Seasonality**: Certain months show higher subscription rates (e.g March has the highest subscription rate, followed by Sep, Oct and Dec). This suggests seasonality in campaign effectiveness.
    - **Correlated features**: There is positive correlation (0.56) between pdays and previous, which suggests that clients who were contacted multiple times (previous high) were typically contacted more recently (pdays lower but positive). The more recent the previous contact (smaller pdays value), the more likely there were multiple previous contacts (previous value higher).
- **Numerical feature variation**: Features like `balance`, `duration`, and `previous` show distributional differences between subscribers and non-subscribers, indicating predictive potential. 
- **Categorical feature variation**: Features such as `marital status`, `housing loan`, and `poutcome` also show differences in subscription rates, suggesting they could be useful predictors.

#### Modeling and Evaluation

1.  **Model Selection:** Base models were evaluated using 5-Fold Stratified Cross-Validation. **Random Forest** and **Gradient Boosting** emerged as the top performers.
2.  **Optimization:** The top two models were optimized using GridSearchCV based on the ROC-AUC metric.
3.  **Final Selection:** The **Tuned Random Forest Model** was selected for its superior performance (ROC-AUC = 0.961).
4.  **Threshold Tuning:** The final model's classification threshold was optimized to 0.30 to maximize the F1-score.

#### Final Results and Key Findings

##### Final Model Performance (Tuned Random Forest, Threshold: 0.30)

| Metric | Score | Interpretation |
| :--- | :--- | :--- |
| **ROC-AUC** | **0.961** | Excellent overall discriminative power. |
| **F1-Score** | **0.696** | Best balance of Precision and Recall. |
| **Recall** | **0.644** | The model correctly identifies 64.4\% of all potential subscribers. |
| **Precision** | **0.757** | 75.7\% of predicted subscriptions are correct, ensuring low wasted outreach. |

#### Key Predictive Features (Feature Importance)

The model revealed the following factors are most critical to predicting a successful subscription:

1. **Call Duration** (Importance: 0.367)
   - Overwhelmingly the most important feature
   - More than 3.5x more influential than the next feature
   - Suggests length of conversation is crucial for prediction
   - Business Implication: Quality time spent with potential customers is critical

2. **Financial Indicators** (Importance: 0.097)
   - Account balance is the second most important feature
   - Indicates customer's financial capacity is relevant
   - Business Implication: Target segmentation by financial status may be effective

3. **Customer Demographics**
   - Age shows moderate importance (0.074)
   - ID significance (0.077) might indicate patterns in customer segments
   - Business Implication: Age-based targeting could be valuable

4.  **Outcome of Previous Campaign (0.038):** Past campaign success is a strong indicator of future conversion.

#### Business Recommendations

- Call Strategy
    - Maximize Quality Conversation Time. The length of the call is the best predictor. Train staff to extend meaningful engagement. Set new KPIs to reward Duration and Conversion Rate, not just call volume.
- Client Targeting
    - Focus on High-Value and 'Warmed-Up' Clients. Prioritize clients with high scores, especially those with high balances or previous success. Use the model's score to limit campaign contacts to the top 20% of potential clients, reducing unnecessary spending on unlikely converts.
- Re-engagement
    - Capitalize on past success. Clients who subscribed before are extremely likely to subscribe again. Immediately flag and re-target all clients with a 'poutcome_success' of 'success' in subsequent campaigns.


#### Next steps
- Deployment: Integrate the final Random Forest model and the 0.30 threshold into the operational CRM system to generate daily, prioritized call lists.
- Feature Engineering: Investigate creating features that combine Duration and Campaign to capture the duration per contact efficiency.
- Advanced Optimization: Consider deploying a model-agnostic explanation tool like SHAP to provide real-time, per-client rationale for the prediction to sales agents.

#### Outline of project
```text
capstone-project/
├── data/
│   └── train.csv
├── notebooks/
│   └── 01_eda.ipynb
│   └── 02_modeling.ipynb
├── final_model.joblib  <-- Saved final model and threshold
└── README.md
```
##### Contact and Further Information
Nachiket Deshpande, nash.deshpande@gmail.com