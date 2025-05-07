# Coupon Acceptance Analysis

This repository contains an analysis of customer coupon acceptance data, focusing on identifying characteristics that influence whether drivers accept coupons for various establishments (restaurants, bars, coffee houses, etc.).

## Data Overview

The dataset, sourced from the UCI Machine Learning repository, includes user demographics (gender, age, marital status, income, etc.), contextual information (driving destination, weather, time of day, passengers), and coupon details. The target variable indicates whether a driver accepted the coupon ('Y = 1') or not ('Y = 0').

## Analysis Summary

The analysis explores several key questions:

1. **Overall Acceptance Rate:**  Determines the proportion of delivered coupons that were accepted.

2. **Coupon Type Impact:** Visualizes the distribution of different coupon types and calculates acceptance rates for each type.  Particular attention was paid to Bar coupons.

3. **Impact of Demographics and Context on Bar Coupon Acceptance:** Examines how factors such as:
    * Frequency of bar visits
    * Age
    * Passengers
    * Occupation 
influence the likelihood of accepting a bar coupon.

4. **Independent Investigation: Coffee House Coupons:** Extends the analysis to Coffee House coupons, exploring relationships between income, age, and acceptance rates.  Provides a template for future analysis of other coupon types.


## Key Findings (Bar Coupons)

* Frequent bargoers show a significantly higher acceptance rate for bar coupons.
* Age appears to play a role, with those over 25 or under 30 showing higher acceptance rates (further statistical tests are recommended).
* Passengers and occupation also seem to influence acceptance, but with less pronounced effects.

## Key Findings (Coffee House Coupons)

* Visualizations provided of acceptance rate against income.


## Further Analysis

While the provided analysis reveals some interesting trends, further investigation using more rigorous statistical methods (t-tests, chi-squared tests, multivariate analysis) would strengthen the conclusions.


## Repository Structure

*   **README.md:** This file.
*   **data/coupons.csv:** Input dataset
*   **images/ (dir)** Visualizations for analysis
*   **hw5_1.ipynb:**  Contains the code for data analysis and visualizations.  Includes exploratory data analysis, data cleaning and statistical summaries.

## Getting Started

To reproduce the analysis:

1. Clone the repository.
2. Make sure you have the required libraries installed (pandas, matplotlib, seaborn).
3. Run the Jupyter Notebook.

## Acknowledgments
UCI Machine Learning Repository for the coupon dataset.
