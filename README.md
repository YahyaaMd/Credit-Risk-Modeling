# Credit Risk Modeling and Analysis

## Overview
This repository contains a comprehensive **Credit Risk Analysis and Modeling** project using a dataset of loan data from 2007 to 2014. The analysis and models developed here are designed to evaluate and predict the **Probability of Default (PD)**, **Loss Given Default (LGD)**, and **Exposure at Default (EAD)** for loans. These metrics are essential for understanding and mitigating financial risks associated with lending.

## Project Objectives
- **Data Preprocessing**: Clean and prepare raw loan data for analysis.
- **Exploratory Data Analysis (EDA)**: Gain insights into key trends and patterns in the dataset.
- **Default Prediction (PD Model)**: Develop and validate a logistic regression model to predict the likelihood of loan defaults.
- **Loss Given Default (LGD Model)**: Model the recovery rate of defaulted loans.
- **Exposure at Default (EAD Model)**: Estimate the credit conversion factor for loans.

## Dataset
The dataset used in this project is publicly available on Kaggle: [Lending Club Loan Data](https://www.kaggle.com/wordsforthewise/lending-club). It contains loan-level data including:
- **Loan Characteristics**: Term, interest rates, funded amount, installment amount.
- **Borrower Details**: Employment length, annual income, home ownership status.
- **Credit History**: Earliest credit line, delinquencies, inquiries in the last six months.
- **Loan Performance**: Loan status, recoveries, and total received principal.

## Repository Structure

### Data Preparation
- **Cleaning and Transformation**: Missing value imputation, feature engineering (e.g., converting categorical variables to dummies, handling dates).
- **Feature Engineering**: Derived features such as `mths_since_earliest_cr_line`, `term_int`, and dummy variables for categorical data.

### Probability of Default (PD) Modeling
- **Target Variable**: Binary variable `good_bad`, indicating default status.
- **Feature Selection**: Selected features such as grade, home ownership, loan purpose, and credit history.
- **Model**: Logistic regression with Weight of Evidence (WoE) transformation for categorical variables.

### Loss Given Default (LGD) Modeling
- **Target Variable**: Recovery rate calculated as `recoveries / funded_amnt`.
- **Data Preparation**: Handle extreme recovery rates (e.g., clipping values to [0, 1]).
- **Model**: Two-stage logistic regression to classify recovery rates as 0 or greater and predict non-zero rates.

### Exposure at Default (EAD) Modeling
- **Target Variable**: Credit conversion factor calculated as `(funded_amnt - total_rec_prncp) / funded_amnt`.
- **Feature Engineering**: Utilized features such as loan term, interest rate, and borrower income.
- **Model**: Regression model to predict EAD values.

## Visualization
- **Histograms and plots**: Recovery rates and credit conversion factors.
- **Weight of Evidence (WoE) plots**: For categorical variables.

## Notebooks and Scripts
- **Credit Risk Modeling.ipynb**: Contains the initial data exploration and preprocessing steps.
- **Credit Risk Modeling Part 2.ipynb**: Focuses on PD modeling and logistic regression.
- **Credit Risk Modeling Part 3.ipynb**: Extends analysis to LGD and EAD models with advanced feature engineering.
- **Credit Risk Modeling Part 4.ipynb**: Includes data visualizations and model performance evaluations.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/YOUR_GITHUB_USERNAME/credit-risk-analysis.git
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the scripts sequentially or load the notebooks for interactive exploration.

## How to Use
1. Replace the dataset path in the scripts with your own path to `loan_data_2007_2014.csv`.
2. Execute each script to preprocess data, build models, and generate results.
3. Adjust model parameters as necessary for further optimization.

## Future Work
- Integrate advanced machine learning algorithms like random forests or XGBoost.
- Extend the analysis to include macroeconomic factors.
- Develop a dashboard for real-time risk monitoring.

## References

### Libraries Used
- **pandas**, **numpy** for data manipulation
- **scikit-learn** for modeling
- **matplotlib**, **seaborn** for visualization

## Acknowledgments
This project is inspired by practical risk management frameworks in financial institutions. Special thanks to the open-source community for providing valuable resources and tools.

## License
This project is licensed under the MIT License. See the LICENSE file for details.
