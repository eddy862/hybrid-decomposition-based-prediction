# A Decomposition-Based Hybrid Time Series Forecasting Framework for River Nitrate Prediction

This repository contains the notebook-based implementation for a final year project on river nitrate forecasting. The project explores a decomposition-based hybrid time series forecasting framework, where nitrate concentration is separated into trend, seasonal, and residual components before training and combining specialised forecasting models.

The main objective is to improve nitrate prediction by comparing hybrid component-level models against direct forecasting baselines. The workflow includes data exploration, preprocessing, decomposition, feature engineering, model training, hyperparameter tuning, and performance comparison.

## Repository Structure

```text
.
|-- analysis.ipynb      # Dataset loading, exploratory data analysis, missing data checks, and visualisation
|-- experiment.ipynb    # Main modelling workflow, decomposition, training, tuning, and evaluation
`-- README.md
```

## Dataset

The notebooks use the Kaggle dataset `ivivan/real-time-water-quality-data`, which contains real-time water quality observations from river monitoring stations. The analysis focuses on river nitrate prediction using time series water quality and hydrological variables.

The dataset is downloaded inside the notebooks using `kagglehub`, so no raw dataset files are committed to this repository.

## Methods

The project workflow includes:

- Exploratory data analysis of river water quality time series.
- Missing data inspection and preprocessing.
- Seasonal-trend decomposition of nitrate concentration.
- Feature engineering, including time-based features and event indicators.
- Component-wise modelling for trend, seasonal, and residual signals.
- Hybrid prediction by recombining component forecasts.
- Baseline comparison using direct forecasting models.
- Evaluation using metrics such as MSE, RMSE, MAE, and R2.

Models and techniques used in the experiments include STL decomposition, ARIMA, Linear Regression, Random Forest, XGBoost, SVR, KNN, MLP, LSTM, GRU, NARNET-style neural models, Random Search, Grid Search, and Whale Optimization Algorithm.

## How to Run

### Option 1: Google Colab

Google Colab is the easiest way to run the notebooks, especially for the deep learning experiments.

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload `analysis.ipynb` or `experiment.ipynb`.
3. For `experiment.ipynb`, enable a GPU runtime if available:
   - `Runtime` > `Change runtime type` > `T4 GPU` or another GPU option.
4. Run the notebook cells from top to bottom.

The notebooks install or import the required packages inside the notebook where needed.

### Option 2: Local Jupyter Notebook

To run locally, use Python with Jupyter Notebook or JupyterLab.

1. Create and activate a virtual environment:

```bash
python -m venv .venv
.venv\Scripts\activate
```

2. Install the main dependencies:

```bash
pip install jupyter pandas numpy matplotlib seaborn scikit-learn statsmodels pmdarima tensorflow xgboost PyWavelets kagglehub
```

3. Start Jupyter:

```bash
jupyter notebook
```

4. Open and run the notebooks:

- Start with `analysis.ipynb` to understand the dataset.
- Run `experiment.ipynb` for the full modelling and evaluation workflow.

## Notes

- The experiment notebook can take a long time to run because it trains multiple models and performs hyperparameter tuning.
- Results may vary slightly between runs due to random initialisation, neural network training, and hardware differences.
- A GPU runtime is recommended for the neural network sections.
- If Kaggle authentication is required locally, configure your Kaggle API credentials before running the dataset download cells.

