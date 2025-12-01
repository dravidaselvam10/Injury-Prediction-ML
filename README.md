Overview:
This repository contains a machine learning framework for predicting rare or high-impact events in longitudinal settings — such as athlete injury risk, equipment failure, or customer churn — where outcomes evolve over time and decisions carry asymmetric costs.

The pipeline demonstrates how to transition from raw time-stamped data to actionable probabilistic forecasts that can inform real-world interventions. It integrates temporal validation, robust metrics for imbalanced data, and a cost-sensitive decision simulation that bridges the gap between predictive performance and business or operational value.

Workflow Summary:
Data Ingestion & Preprocessing: Reads structured time-series data (e.g., session, week, or day-level), Handling missing values, categorical encodings, and sorting by entity and timestamp.
Temporal Data Splitting: Generates multiple rolling windows (train/validation/test) that move chronologically through time.
Model Training & Evaluation: Trains candidate models on each window, computing key metrics (PR-AUC, ROC-AUC, recall@precision) and compares against naïve temporal baselines.
Bootstrap-Based Uncertainty Analysis: Produces confidence intervals for all key metrics via stratified resampling.
Policy Simulation & Decision Optimisation: Sweeps thresholds to identify operating points that minimise expected cost under given assumptions of false positive and false negative impact.
Visualisation & Reporting: Generates summary figures such as precision–recall curves, cost curves, and calibration plots.

To reproduce the core results presented in this work, follow these steps:

Clone the repository:

git clone https://github.com/dravidaselvam10/Injury-Prediction-ML.git


Install dependencies:

Using pip:

pip install -r requirements.txt


Or with Conda (if environment.yml is provided):

conda env create -f environment.yml
conda activate injury-ml-env


Execute model training and evaluation:

Run the appropriate scripts or Jupyter notebooks included in the /src and /notebooks folders.

Follow dataset-specific instructions outlined in the README to ensure proper data loading and feature engineering.

Validate results:

Use the provided logs and notebook outputs to verify reported metrics (AUC, F1, Recall).

All model parameters and random seeds (e.g., RANDOM_SEED=42) are fixed to support deterministic outcomes.

The repository includes:

🧾 README.md with structured documentation

📊 Training/evaluation notebooks for classical and deep models

⚙ Preprocessing utilities for workload harmonization

🔧 Model configuration files for reproducibility and tuning

📝 Data documentation (feature definitions and injury label guidance)

This reproducible workflow enables researchers, practitioners, and reviewers to validate the results, adapt the pipeline to new datasets, and benchmark across sports or leagues.
