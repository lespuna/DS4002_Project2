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

