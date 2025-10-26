# Project 2 - Predicting Housing Prices Based on Time and Location

## Data Devils: Laura Espuna (leader), Anthony Jiang

### Software & Platform

#### Platform Used
- Development was done primarily on **macOS (Sonoma 14.0)**.
- It should also run on **Windows 10/11** as long as **Python 3.11** and the required packages are installed.

#### Software Used
- **Programming Language:** Python 3.11
- **Version Control:** Git and Github
- **IDE (recommended):** VS Code or Jupyter Notebook

- #### Required Packages
  The following Python packages are required to run the project:
  - `pandas` (for dataset manipulation and storage)
  - `numpy` (for numerical computations)
  - `matplotlib` (for visualization)
  - `scikit-learn` (for feature extraction, model training, and evaluation)
  - `seaborn` (for statistical visualization)
  - `statmodels` (for statistical modeling)
 
  - To install, run the following code:
  ```
  pip install -r requirements.txt
  ```

### Map of Repository
```
.
├── DATA
│   ├── Metro_zhvi_uc_sfrcondo_tier_0.33_0.67_sm_sa_month.csv
│   ├── README.md
│   └── zhvi_clean_long.csv
├── LICENSE
├── OUTPUTS
│   ├── eda_multicity_indexed.png
│   ├── eda_multicity_levels.png
│   ├── eda_multicity_yoy.png
│   ├── sarima_backtest_results.csv
│   ├── sarima_success_by_region.csv
│   └── sarima_summary_by_horizon.csv
├── README.md
├── requirements.txt
└── scripts
    ├── data_cleaning.ipynb
    ├── data_exploration.ipynb
    └── model_building.ipynb

4 directories, 15 files

```

### Instructions for Reproduction

#### Step 0: Environment Setup

Clone the repository:
```
git clone <your_repo_url>
cd DS4002_Project2

```

Create and activate a virtual environment:
```
python3 -m venv venv
source venv/bin/activate      # macOS/Linux
venv\Scripts\activate         # Windows
```

Install all required dependencies:
```
pip install -r requirements.txt
```

#### Step 1: Data Cleaning

Navigate to the `SCRIPTS/` folder and `open data_cleaning.ipynb`

This notebook:
- Loads the Zillow Home Value Index (ZHVI) dataset from DATA/.
- Filters for selected metros (New York, Los Angeles, Chicago, Miami, San Francisco).
- Converts date values to month-end format and reshapes into long format.

The cleaned dataset is saved as `zhvi_clean_long.csv` in the `DATA/` directory.

#### Step 2: Exploratory Data Analysis

Open `data_exploration.ipynb`

This notebook:
- Visualizes housing price trends and seasonality across metros.
- Explores correlations and long-term growth patterns.
- Generated figures (ex. EDA plots) are exported to the `OUTPUTS/` folder.

#### Step 3: Model Building and Backtesting

Open `model_building.ipynb`

The notebook performs the full SARIMA modeling pipeline:
- Ensures monthly frequency and consistent time indexing.
- Suggests differencing orders (d, D) using ADF/KPSS tests.
- Runs a grid search over candidate (p,d,q)(P,D,Q)_m configurations.
- Conducts rolling-origin backtests with training, validation, and testing folds.
- Computes error metrics (MAPE, sMAPE, RMSE, MAE) for each forecast horizon (3, 6, and 12 months).

Intermediate and final results are saved in the `OUTPUTS/` folder as:
- `sarima_backtest_results.csv`
- `sarima_summary_by_horizon.csv`
- `sarima_success_by_region.csv`

#### Step 4: Model Evaluation and Diagnostics

Evaluate model performance using aggregated results in the summary CSVs.
Run the “Diagnostics on One Example Fit” cell in `model_building.ipynb` to visualize:
- Residual autocorrelation (ACF) plots
- Normality (Q–Q) plots

These help confirm that model residuals behave like white noise and the SARIMA specification is appropriate.

#### Step 5: Reproduce Results

To fully reproduce project results:
Run notebooks sequentially in this order:
- `data_cleaning.ipynb`
- `data_exploration.ipynb`
- `model_building.ipynb`

Verify that output files and plots appear in the `OUTPUTS/` directory.