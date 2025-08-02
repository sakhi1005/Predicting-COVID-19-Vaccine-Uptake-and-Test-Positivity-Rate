Predicting COVID-19 Vaccine Uptake and Test Positivity Rate

This repository contains a Jupyter Notebook (MLPS_Project_Covid_Predictions.ipynb) that explores, models, and visualizes county-level forecasts of COVID-19 vaccination coverage and 14-day test positivity rates using supervised regression techniques.

📋 Project Structure

├── MLPS_Project_Covid_Predictions.ipynb  # Main analysis and modeling notebook
├── covidcast_new-2.csv                  # Raw CTIS survey data (county-day records)
├── df_pos_imputed.csv                   # Preprocessed dataset for positivity modeling
├── requirements.txt                     # Python dependencies
└── README.md                            # Project overview and instructions

🔍 Dataset

Source: CMU Delphi COVID-19 Trends and Impact Survey (CTIS) via Facebook

Dates: January 7 – February 12, 2021

Records: 25,627 county-day observations

Features:

smoothed_wcovid_vaccinated (target: vaccination %)

smoothed_wtested_positive_14d (target: test positivity rate)

Multiple behavioral and belief indicators (mask usage, mobility, vaccine confidence, etc.)

🚀 Getting Started

1. Clone this repository

git clone https://github.com/<your-username>/covid-predictions.git
cd covid-predictions

2. Create a virtual environment and install dependencies

python3 -m venv venv
source venv/bin/activate       # macOS/Linux
venv\Scripts\activate        # Windows
pip install -r requirements.txt

3. Place the data files

Download or move covidcast_new-2.csv and df_pos_imputed.csv into the project root.

4. Launch Jupyter Notebook

jupyter notebook MLPS_Project_Covid_Predictions.ipynb

🖥 Notebook Overview

EDA

Data exploration, summary statistics, missing-value imputation, and correlation analysis.

Model Building

Definition of a reusable modeling() function to train and compare multiple regressors (Linear Regression, Ridge, Lasso, Random Forest, etc.).

Visualization of Actual vs. Predicted values and selection of the best-performing model.

Targeted Model

modeling_with_4features() for streamlined forecasting using a subset of four key predictors.

Evaluation

Calculation of R², RMSE, and MAE for each model.

Scatter plots and Pearson correlation between predicted vaccination uptake and test positivity.

📊 Results

High-accuracy forecasts of vaccination coverage and test positivity across U.S. counties.

Visual diagnostics (Actual vs. Predicted) saved as PNGs in the project directory.

Insights to inform resource allocation and targeted public health interventions.

⚙️ Requirements

Python 3.7+

pandas

numpy

matplotlib

seaborn

scikit-learn

scipy

You can install all dependencies via: pip install -r requirements.txt

📝 License

This project is released under the MIT License. See LICENSE for details.

🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request with improvements or new features.

Created by Sakhi Khanchandani, MISM candidate at Carnegie Mellon University.
