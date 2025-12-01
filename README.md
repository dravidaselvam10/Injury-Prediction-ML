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
