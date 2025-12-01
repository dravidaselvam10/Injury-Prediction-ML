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

This study ensures reproducibility and transparency through open access to all source code, preprocessing routines, and model configurations. The complete implementation— including data ingestion scripts, model training pipelines, and evaluation workflows—is publicly available at:
To reproduce the core results presented in this work, follow these steps:
1) Clone the repository: git clone https://github.com/dravida-selvam10/Injury-Prediction-ML.git
2) Install dependencies:
• Using pip: requirements.txt
3) Execute model training and evaluation: Use the scripts and notebooks. Dataset-specific instructions are included in the README to ensure proper loading and preprocessing.
The repository includes:
• README.md: Project documentation and usage instructions
• Notebooks: Training and evaluation for classical and deep models
• Data Descriptions: Feature definitions and label conventions
This reproducible framework enables practitioners and researchers to validate results, extend the pipeline to other datasets, and benchmark model performance across sports or leagues.
