# Electric Vehicle Data Analysis for CAFV Eligibility

**Author:** Nachiket Deshpande 

#### Executive summary
This project analyzes the **Electric Vehicle Population dataset (2025)** to explore patterns in electric vehicle (EV) adoption across the U.S. and to build predictive models for **Clean Alternative Fuel Vehicle (CAFV) eligibility**. The study aims to provide insights into which EV attributes most strongly determine eligibility and to support policymakers, manufacturers, and consumers with data-driven findings.  

#### Rationale
CAFV eligibility determines access to high-occupancy vehicle (HOV) lanes, tax incentives, and other policy benefits that encourage EV adoption. By predicting eligibility, we can better understand which vehicle attributes are most critical for meeting regulatory standards, and provide insights to consumers and policymakers about the future EV market.

#### Research Question
Can we predict whether an electric vehicle (EV) qualifies for Clean Alternative Fuel Vehicle (CAFV) eligibility based on its attributes such as make, model year, electric range, and vehicle type (BEV vs PHEV)?

#### Data Sources
I will be using the Electric Vehicle Population dataset (2025) Links to an external site.from Kaggle, which contains over 170,000 EV registration records across the U.S.

**Dataset**: [Electric Vehicle Population Dataset (2025) – Kaggle](https://www.kaggle.com/datasets/yanghu583/electric-vehicle-population-data-2025)  
- **Size**: ~170,000 EV registration records  
- **Fields include**: Make, Model, Model Year, EV Type (BEV/PHEV), Electric Range, CAFV Eligibility, Location (State, County, City), and Utility provider.  


#### Methodology
I plan to apply supervised machine learning classification techniques such as logistic regression, random forest, and gradient boosting. Data preprocessing will include handling missing values, encoding categorical features (make, model, type), and scaling numerical features (e.g., range, year). I will evaluate the models using accuracy, precision, recall, F1-score, and ROC-AUC.

#### Results
Modeling TBD, but I expect that EV range, vehicle type (BEV vs PHEV), and model year will strongly influence CAFV eligibility predictions. A well-tuned ensemble model should provide reliable predictions with solid interpretability through feature importance analysis.

#### Next steps
- Complete preprocessing and modeling pipeline  
- Run comparative experiments across classifiers  
- Document insights in a final presentation/report 

#### Outline of project
*   [README.md](https://github.com/nashdeshpande/berkeley-ai-ml/edit/main/capstone-project/README.md) : This file.
*   [data/Electric_Vehicle_Population_Data.csv](https://github.com/nashdeshpande/berkeley-ai-ml/blob/main/capstone-project/data/Electric_Vehicle_Population_Data.csv) : (Input dataset)
*   [notebook.ipynb](https://github.com/nashdeshpande/berkeley-ai-ml/blob/main/capstone-project/notebook.ipynb) : Contains the code for data analysis and visualizations. 

##### Contact and Further Information
Nachiket Deshpande, nash.deshpande@gmail.com
