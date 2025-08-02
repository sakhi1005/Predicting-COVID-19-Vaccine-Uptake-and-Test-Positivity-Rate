Predicting COVID-19 Vaccine Uptake and Test Positivity Rate

Authors:

Yash Sivramkrishnan (ysivramk@andrew.cmu.edu)

Sachi Shah (sachipas@andrew.cmu.edu)

Aritra Dutta (aritrad@andrew.cmu.edu)

Sakhi Khanchandani (skhancha@andrew.cmu.edu)

📖 Overview

Forecast county-level COVID-19 vaccination coverage and 14-day test positivity rates using supervised regression models built on behavioral and belief indicators from the CMU Delphi CTIS Facebook survey.

📂 Project Structure

├── MLPS_Project_Covid_Predictions.ipynb    # Exploration, modeling & visualization
├── covidcast_new-2.csv                    # Raw CTIS data (county-day records)
├── df_pos_imputed.csv                     # Preprocessed positivity dataset
├── requirements.txt                       # Python package list
└── README.md                              # This file

🗄️ Dataset

Source: CMU Delphi CTIS via Facebook

Timeframe: Jan 7 – Feb 12, 2021

Records: 25,627 county-day observations

Features:

COVID activity: symptoms, test results, vaccination status

Behavioral: mask usage, mobility patterns

Belief: vaccine confidence in WHO, government, peers

Targets:

smoothed_wcovid_vaccinated (vaccination %)

smoothed_wtested_positive_14d (14‑day test positivity)

🔍 Data Analysis

Cleaning & Imputation

Dropped records with >80% missing positivity data

Mean-imputed remaining gaps (< 20%)

Correlation & Feature Selection

Detected multicollinearity among predictors (ρ > 0.85)

Selected top 4 predictors for reduced-feature experiments

🛠️ Modeling Approach

Step

Details

Baseline

OLS Regression with 5‑fold CV, standard scaling, mean imputation

Algorithms

Ridge, Lasso, Random Forest, KNN, MLP

Reduced-Feature Try‑out

Top 4 predictors per target

Metrics

R², RMSE, MAE (cross‑validation & test set)

Reusable pipelines: modeling() and modeling_with_4features() for consistency.

📈 Key Findings

KNN (full features):

Vaccination: R² ≈ 0.90

Positivity: R² ≈ 0.905

KNN (top 4 features):

Vaccination: R² ≈ 0.67

Positivity: R² ≈ 0.87

Insight: Strong negative correlation (ρ ≈ –0.72) between predicted uptake and positivity confirms vaccination’s protective effect.

🚀 Setup & Usage

Clone repository

git clone https://github.com/<username>/covid-predictions.git
cd covid-predictions

Install dependencies

python3 -m venv venv
source venv/bin/activate        # macOS/Linux
venv\\Scripts\\activate       # Windows
pip install -r requirements.txt

Add dataPlace covidcast_new-2.csv and df_pos_imputed.csv in the project root.

Run notebook

jupyter notebook MLPS_Project_Covid_Predictions.ipynb

⚙️ Requirements

Python: ≥ 3.7

Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, scipy

pip install -r requirements.txt

📃 License

Released under the MIT License.

🤝 Contributing

Contributions welcome! Please open issues or submit pull requests to improve models, docs, or visualizations.


