# Sales Forecasting and Demand Prediction

This repository contains a Streamlit demo, a saved Keras model, a Jupyter notebook, and project documentation for a retail sales and demand forecasting project.

## Repository contents

- `App/streamlit_app.py` and `App/best_demand_forecast_model.keras` — demo UI and saved model.
- `notebooks/Sales_Forecasting_and_Demand_Prediction.ipynb` — exploratory analysis and modeling notebook.
- `ML flow.py` — MLflow experiment code that expects training and test variables to have already been prepared.
- `src/Final Doc.pdf` and `src/Final Presentation.pdf` — project deliverables.
- `src/requirements` — pinned Python dependencies for the project and app.

## Run the Streamlit demo

Use Python 3.11 in a virtual environment. From the repository root:

```bash
python -m venv .venv
# Linux/macOS: source .venv/bin/activate
# Windows PowerShell: .\\.venv\\Scripts\\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r src/requirements
streamlit run App/streamlit_app.py
```

The app resolves its bundled model relative to its own source file, so it does not depend on the shell's current directory. See [`Deployment`](Deployment) for the same launch instructions.

## Notebook data

The notebook references the [Retail Store Inventory Forecasting Dataset on Kaggle](https://www.kaggle.com/datasets/anirudhchauhan/retail-store-inventory-forecasting-dataset), but the dataset is **not included** in this repository. The notebook looks by default for `data/retail_store_inventory.csv` relative to the notebook process's current directory. To use another location, set `RETAIL_DATA_PATH` to the CSV path before starting Jupyter. The notebook stops with a clear missing-file error rather than relying on a machine-specific Windows path.

Do not commit private datasets, credentials, or locally generated files to this repository.

## Reproducibility and limitations

- The saved model is present, but its loading and predictions were not validated in this repository checkout. TensorFlow is required to run the app.
- No training dataset or prepared train/test split is checked in. Consequently, model metrics and training results cannot be independently reproduced from this checkout. No performance claim is made here.
- `ML flow.py` is not a standalone training entry point: it references data/model variables expected to exist in a prepared notebook session. The notebook and model results should be reviewed before using predictions for operational decisions.
- This demo is for exploration only, not a validated production forecasting service.
