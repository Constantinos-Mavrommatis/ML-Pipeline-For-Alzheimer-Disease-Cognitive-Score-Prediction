# ADNI-ADAS13-Prediction

Predict the 24‑month ADAS‑Cog 13 cognitive score using baseline clinical, demographic, genetic and MRI features from ADNI, via a Lasso model with polynomial (interaction‑only) features.

## Overview

- End‑to‑end workflow in a Jupyter notebook (`notebooks/ADNI-ADAS13-Prediction.ipynb`).
- Preprocessing with `ColumnTransformer`: median imputation (numeric), one‑hot encoding (categorical), ordinal encoding (DX.bl), standardization.
- Final model: **Lasso** with degree‑2 **interaction‑only** polynomial features, tuned by **GridSearchCV**.
- Outputs include diagnostic plots and coefficient tables; see the **Report.pdf** in `docs/` for a narrative summary.

## Key results (from the Report)

- **Lasso (polynomial)** test metrics: **MSE ≈ 30.97**, **RMSE ≈ 5.56**, **R² ≈ 0.813**.  
- Baseline linear regression test metrics: **MSE ≈ 34.08**, **RMSE ≈ 5.84**, **R² ≈ 0.795**.  

See `docs/Report.pdf` for details.

## Getting started

### Option A: Conda
```bash
conda env create -f environment.yml
conda activate adni-adas13
jupyter lab
```

### Option B: pip + venv
```bash
python3 -m venv .venv
source .venv/bin/activate    # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook
```

Then open `notebooks/ADNI-ADAS13-Prediction.ipynb`, set the data path to `data/adnidata.csv`, and run all cells.

## Repo structure

```
ADNI-ADAS13-Prediction/
├─ notebooks/
│  └─ Final_Version.ipynb
├─ docs/
│  ├─ Final_Report.pdf
│  └─ Project_Description.pdf
├─ requirements.txt
├─ environment.yml
├─ CITATION.cff
└─ LICENSE
```

## Acknowledgements

- Authors: **Constantinos Mavrommatis**, **Matt Carre**
- Dataset: Alzheimer’s Disease Neuroimaging Initiative (ADNI) — reduced coursework version.
- Course: *Machine Learning in Python (2024‑2025)*.
