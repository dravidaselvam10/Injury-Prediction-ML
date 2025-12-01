# MLBA-Injury-Prediction (Project repo)

This repository contains a reproducible pipeline for injury risk prediction using time-series athlete load features. It includes:
- data generation (toy AFL dataset)
- preprocessing & feature engineering
- model training (Logistic Regression, Random Forest, XGBoost, BiLSTM)
- evaluation (AUC-ROC, AUC-PR, precision/recall/f1, calibration)
- interpretability (SHAP)
- artifacts saved to `outputs/`.

## Quick start

1. Create a virtual environment and install dependencies:
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

2. Generate toy data:
```bash
python toy_data/generate_toy_data.py
```

3. Run experiment end-to-end:
```bash
python src/train.py --config configs/config.yaml
```

4. Evaluate:
```bash
python src/evaluate.py --config configs/config.yaml
```

Outputs (models, plots) appear in `outputs/`.

See `src/` for all code.

## Notes
- This pipeline uses time-based splits to avoid leakage.
- The toy data is synthetic for reproducibility; replace `toy_data/toy_afl.csv` with your club data (same schema) for real experiments.
