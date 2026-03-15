# Nova Scotia Power Electricity Analytics

This repository contains the completed MCDA 5580 Data and Text Mining assignment, focusing on electricity analytics for Nova Scotia Power Inc (NSPI). The project encompasses Exploratory Data Analysis, Time Series Forecasting, Anomaly Detection, and Tableau Dashboard Data Preparation.

## Project Structure

- `Assignment.ipynb`: The main Jupyter Notebook containing all Python code, visualizations, and markdown explanations for Task 1 (EDA) and Task 2 (Forecasting & Anomaly Detection).
- `Tableau_Dashboard_Guide.md`: 📊 **Crucial:** Step-by-step instructions for developing the final interactive Tableau Dashboard (Task 3).
- `tableau_historical_data.csv`: The cleaned and enriched dataset containing Isolation Forest anomaly flags, used for the historical Tableau visualizations.
- `tableau_forecast_data.csv`: A dedicated dataset specifically structured for comparing Actuals vs. Prophet Forecast vs. LSTM Forecast in Tableau.
- `nsp_electricity_dataset.csv`: The original raw dataset (not included in version control due to file size).

## Getting Started

### 1. Python Analysis (Tasks 1 & 2)
The project utilizes `uv` for dependency management and execution. To review the analysis, open `Assignment.ipynb`. 

To re-execute the notebook from top to bottom and regenerate the Tableau CSVs:

```bash
uv run --with jupyter --with pandas --with numpy --with matplotlib --with seaborn --with prophet --with scikit-learn --with tensorflow jupyter nbconvert --to notebook --execute --inplace Assignment.ipynb
```

### 2. Tableau Dashboard Development (Task 3)
To construct the final interactive deliverable for the non-technical executive audience, assemble the Tableau dashboard using the generated datasets.

👉 **Please read the [Tableau Dashboard Guide](Tableau_Dashboard_Guide.md) for complete instructions.**

The guide maps out exactly how to connect `tableau_historical_data.csv` and `tableau_forecast_data.csv` to Tableau effectively, providing instructions to recreate all **8 required visualizations** and the interactive filters.
