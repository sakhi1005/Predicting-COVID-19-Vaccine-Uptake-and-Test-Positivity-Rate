Predicting COVID-19 Vaccine Uptake and Test Positivity Rate

Authors:

Yash Sivramkrishnan (ysivramk@andrew.cmu.edu)

Sachi Shah (sachipas@andrew.cmu.edu)

Aritra Dutta (aritrad@andrew.cmu.edu)

Sakhi Khanchandani (skhancha@andrew.cmu.edu)

1. Title

Predicting COVID-19 Vaccine Uptake and Test Positivity Rate Using Behavioral and Belief Indicators

2. Introduction

This project develops supervised regression models to forecast county-level COVID-19 vaccination coverage and 14-day test positivity rates. By leveraging behavioral and belief indicators from a large-scale survey, the models enable targeted interventions, optimized resource allocation, and improved outbreak control strategies.

3. Dataset

Source: CMU Delphi COVID-19 Trends and Impact Survey (CTIS) via Facebook

Period: January 7–February 12, 2021

Records: 25,627 county-day observations

Features:

COVID activity (symptoms, test results, vaccination status)

Behavioral (mask usage, mobility patterns)

Belief (vaccine confidence in various institutions)

Targets:

smoothed_wcovid_vaccinated (vaccination percentage)

smoothed_wtested_positive_14d (14-day test positivity rate)

4. Data Analysis

Cleaning & Imputation:

Removed records with excessive missing values,

Applied mean imputation for remaining gaps.

Correlation Analysis:

Identified multicollinearity among predictors,

Selected four top features for reduced experiments.

5. Methods & Modeling

Baseline: Ordinary least squares regression with 5-fold cross-validation.

Model Suite: Ridge, Lasso, Random Forest, K-Nearest Neighbors, and Multi-Layer Perceptron.

Reduced-Feature Models: Experiments using top-four predictors.

Evaluation Metrics: R², RMSE, and MAE on both cross-validation and holdout test sets.

6. Key Results

Best performance achieved by K-Nearest Neighbors: R² ≈ 0.90 for vaccination and R² ≈ 0.905 for positivity using full feature sets.

Reduced-feature KNN models still delivered strong results: R² ≈ 0.67 (vaccination) and R² ≈ 0.87 (positivity).

Negative correlation between predicted uptake and positivity (r ≈ –0.72) underscores vaccination’s protective effect.

7. Project Structure

├── MLPS_Project_Covid_Predictions.ipynb    # Notebook with EDA, modeling, and visualizations
├── covidcast_new-2.csv                    # Raw CTIS survey data
├── df_pos_imputed.csv                     # Preprocessed dataset for positivity modeling
├── requirements.txt                       # Python dependencies
└── README.md                              # Project overview and instructions

8. Setup Instructions

Clone the repository:

git clone https://github.com/<username>/covid-predictions.git
cd covid-predictions

Install dependencies:

python3 -m venv venv
source venv/bin/activate       # macOS/Linux
venv\Scripts\activate        # Windows
pip install -r requirements.txt

Add data files (covidcast_new-2.csv, df_pos_imputed.csv) to the project root.

Launch Jupyter Notebook:

jupyter notebook MLPS_Project_Covid_Predictions.ipynb

9. Requirements

Python 3.7 or higher

pandas

numpy

matplotlib

seaborn

scikit-learn

scipy

Install all dependencies with:

pip install -r requirements.txt

10. License

This project is released under the MIT License. See LICENSE for details.
