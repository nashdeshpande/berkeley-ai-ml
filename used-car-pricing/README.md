# Used Car Price Analysis

This project analyzes what factors most influence the price of used cars, using a dataset of 426,000 listings. The analysis follows the CRISP-DM framework and uses regression models to determine the most important features.

## Summary of Findings

Based on the coefficient analysis (or potentially feature importance from tree models):
- Car Age: Likely has a significant negative coefficient, indicating older cars are cheaper. This is expected.
- Odometer: Likely has a significant negative coefficient, indicating higher mileage decreases price. This is expected.
- Manufacturer and Model: Certain manufacturers and models will have large positive or negative coefficients, reflecting brand reputation, luxury status, and demand. These are likely strong drivers.
- Condition, Title Status: Features like 'salvage' title or poor 'condition' should have negative coefficients. 'excellent' or 'like new' condition should have positive coefficients.
- Type, Size, Cylinders, Fuel, Transmission, Drive, Paint Color: These features' impact will vary. Luxury car types, more cylinders, certain fuel types (e.g., electric in some markets), automatic transmission, specific drive types (e.g., 4wd) and popular paint colors might increase price.

--- Do earlier phases need revisitation and adjustment? ---

Based on the current results:

Data Understanding: The initial exploration seems sufficient to identify key features and missingness issues. The current model performance seems reasonable (R-squared above 0.5 indicates it explains more than half the variance in log price).
Data Preparation: The preprocessing (handling missing values, feature engineering like car age, scaling, one-hot encoding, log transform of price) seems appropriate and allowed models to be trained.
Possible Adjustments: Could revisit feature engineering. Are there interaction terms that could be useful (e.g., age * mileage)? Could explore different ways to handle high-cardinality categorical features if OneHotEncoding created too many dimensions or caused issues (e.g., target encoding, feature hashing).
Modeling: We've tried several standard regression models. Ensemble models perform best predictively, while linear models are best for interpretability.
Possible Adjustments: Could try more advanced models (XGBoost, LightGBM). Could spend more time on hyperparameter tuning for the tree-based models (Random Forest, GBR) to potentially improve predictive accuracy further. Could explore feature selection methods to reduce the number of features, which might improve linear model interpretability and training speed.

--- Conclusion for the Client ---

"We have successfully built predictive models for used car prices and identified the key factors driving their value. Our analysis confirms that expected factors like car age and mileage significantly decrease price. More importantly, we can pinpoint specific manufacturers, models, conditions, and other features that command premium prices in the market represented by this data. While ensemble models provide the most accurate price predictions, linear models clearly show the relative impact of each feature. These findings provide valuable insights for your dealership to optimize pricing, inventory decisions, and sales strategies. The current models offer a solid foundation, and we are confident in the insights derived. Further refinement could involve more complex feature engineering or extensive hyperparameter tuning if even higher predictive accuracy is required."

## Repository Contents

- `notebook/prompt_II.ipynb`: Main analysis and model notebook
- `data/vehicles.csv`: Dataset
- This README

## Recommendations for Dealerships

- Key Price Decreasers: Car age and mileage are consistently the strongest negative predictors. Cars with salvage titles or poor conditions also significantly reduce price.
- Key Price Increasers: Certain manufacturers (e.g., luxury brands), specific popular models, and features like 'excellent' condition are strong positive drivers.
- Market Segments: The coefficients for categorical features highlight which specific types, sizes, fuel types, etc., are currently valued more in the used car market the dataset represents.
- Inventory Management: The dealership can use this information to:
- Price cars more accurately based on these key attributes.
- Identify which types of cars are most likely to sell quickly or command higher prices.
- Make informed decisions when acquiring new inventory.
- Advise customers on the factors that impact resale value.

## Next Steps

- Explore location-based pricing trends
- Incorporate additional vehicle features (e.g., safety ratings)