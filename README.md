# ISA 444 — Hotel Occupancy Forecasting ProjectThis is our Final Project for ISA 444 - Business Forecasting

**Authors:** Laci & Figurella | Miami University, Farmer School of Business

## Overview
This project forecasts daily hotel occupancy rates across 17 hotels using 
a range of statistical, machine learning, and foundation models from the 
Nixtlaverse and TimeCopilot ecosystems. We use 5-fold time-series 
cross-validation with a 28-day horizon to compare models.

## Dataset
- 17 hotel time series, daily frequency
- Date range: January 2022 – June 2023
- Target variable: occupancy rate (y), normalized between 0 and 1

## Models Compared
| Family | Models |
|--------|--------|
| Baseline | Naive, SeasonalNaive (LastWeek, LastMonth) |
| StatsForecast | AutoETS, MSTL, AutoARIMA (weekly & monthly) |
| ML | LightGBM via MLForecast |
| Neural | AutoNBEATS, AutoNHITS via NeuralForecast |
| Foundation | TimesFM-2.5, Chronos, Moirai, TabPFN via TimeCopilot |

## Key Findings
- **Best model: TimesFM-2.5** with 26 total wins across all series and metrics
- Weekly seasonality models consistently outperformed monthly counterparts
- MAPE was excluded for series with near-zero occupancy values, as it becomes undefined or extremely inflated — MAE and RMSE were used as primary metrics instead
- Foundation models showed the largest advantage on volatile, low-occupancy hotels
- AutoARIMAWeek was the strongest traditional statistical model

## Project Files
| File | Description |
|------|-------------|
| `ISA_444_Project_May6th.ipynb` | Full modeling notebook with all code |
| `cv_results.csv` | Raw cross-validation results |
| `t_cv_results.csv` | TimeCopilot cross-validation results |
| `evaluation_metrics.csv` | ME, MAE, RMSE, MAPE by series and model |
| `wins_summary.csv` | Win counts per model across all metrics |

## Reproducibility
All models use the Nixtlaverse and TimeCopilot packages only.
Install dependencies with:
```
pip install statsforecast neuralforecast mlforecast timecopilot
```


[This is the link to a public collab](https://colab.research.google.com/drive/1DeDeKUzb_QiK7au-f24IgE2nNctoHFJB?usp=sharing)
