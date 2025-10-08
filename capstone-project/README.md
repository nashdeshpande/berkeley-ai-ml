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
Modeling is TBD, EDA results are as follows:
- **Dataset structure**: The dataset contains 45,211 entries with 17 features. No missing values were found, and no duplicate rows were detected.  
- **Class imbalance**: The dataset is imbalanced. A much smaller proportion of customers (12%) subscribed compared to those who did not (88%). This will require resampling or class-weight adjustments during modeling.
**Outliers**: Some extreme values were observed in numerical features, particularly in `balance` (very high account balances), `pdays` (values up to 999 indicating no previous contact), and `campaign` (clients contacted dozens of times). These may need treatment or capping before modeling.
- **Target variable relationships**: 
- **Education and job**: Students (34%) and retirees (24%) seem to subscribe the most. Customers with higher education (tertiary) seem to subscribe more than other levels of education (16%).
- **Numerical feature variation**: Features like `balance`, `duration`, and `previous` show distributional differences between subscribers and non-subscribers, indicating predictive potential. 
- **Categorical feature variation**: Features such as `marital status`, `housing loan`, and `poutcome` also show differences in subscription rates, suggesting they could be useful predictors.
- **Campaign fatigue**: Subscription rates decline (from approx 18% to 5%) as the number of campaign contacts increases, consistent with customer fatigue. This is also seen in the correlation heatmap (-0.08 correlation between campaign and y)
- **Duration**: Longer call durations are strongly associated with higher subscription likelihood — this may become a key driver in modeling. This shows up in the correlation heatmap with +0.52 between duration and y.
- **Seasonality**: Certain months show higher subscription rates (e.g March has the highest subscription rate, followed by Sep, Oct and Dec). This suggests seasonality in campaign effectiveness.
- **Correlated features**: There is positive correlation (0.56) between pdays and previous, which suggests that clients who were contacted multiple times (previous high) were typically contacted more recently (pdays lower but positive). The more recent the previous contact (smaller pdays value), the more likely there were multiple previous contacts (previous value higher).


#### Next steps
- Complete EDA with detailed visualizations and summary insights  
- Train and evaluate baseline models (logistic regression, decision tree)  
- Experiment with ensemble models (Random Forest, Gradient Boosting, XGBoost)  
- Address imbalance through resampling or advanced techniques (SMOTE, stratification)  
- Summarize key business insights and recommendations for campaign optimization

#### Outline of project
```text
capstone-project/
├── data/
│   └── train.csv
├── notebook.ipynb
└── README.md
```
##### Contact and Further Information
Nachiket Deshpande, nash.deshpande@gmail.com