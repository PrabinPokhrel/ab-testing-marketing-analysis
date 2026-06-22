# E-commerce Revenue Forecasting and Anomaly Detection

End-to-end revenue forecasting and anomaly detection pipeline built on
the UCI Online Retail II dataset (1M+ transactions, UK e-commerce, 2009-2011).

## Business Problem

An e-commerce company needs to predict next 30 days of revenue and get
automatically alerted when daily sales deviate significantly from expected
patterns — without manual intervention.

## Results

| Metric | Value |
|--------|-------|
| Total transactions analysed | 805,549 |
| Daily revenue data points | 604 days |
| Average daily revenue | £29,376 |
| Peak daily revenue | £184,367 (Dec 2011 Christmas peak) |
| Prophet forecast MAPE | 39.51% |
| ARIMA baseline MAPE | 31.79% |
| Anomalies detected | 31 days (5.1%) |
| Revenue spikes flagged | 20 days |
| Revenue dips flagged | 11 days |

## Key Findings

- ARIMA outperformed Prophet on this dataset due to the truncated
  Christmas peak test window — an honest and realistic analytical outcome
- Average spike revenue (£83,655) is 3x normal daily revenue (£27,720)
- The lowest dip (£4,886 on 22 Dec 2010) reflects a Christmas Eve
  half-day trading pattern
- Sunday trading is consistently zero throughout — confirmed retail closure

## Tech Stack

- Python: Pandas, NumPy, Prophet, Statsmodels, Scikit-learn
- Visualisation: Matplotlib, Seaborn, Plotly
- Database: SQL Server
- BI: Power BI
- Automation: GitHub Actions (daily scheduler)

## Project Structure

ecommerce-revenue-forecasting/

├── data/                        # CSV outputs (raw Excel excluded via .gitignore)

├── notebooks/

│   ├── 01_eda.ipynb             # Data cleaning and exploratory analysis

│   ├── 02_forecasting.ipynb     # Prophet and ARIMA forecasting

│   └── 03_anomaly.ipynb         # Isolation Forest anomaly detection

├── src/

│   └── pipeline.py              # Automated daily pipeline

├── dashboard/

│   └── revenue_forecast.pbix    # Power BI dashboard

└── .github/

└── workflows/

└── daily_run.yml        # GitHub Actions scheduler

## Dataset

UCI Online Retail II Dataset — publicly available at:
https://archive.ics.uci.edu/dataset/502/online+retail+ii

## How to Run

```bash
pip install -r requirements.txt
python src/pipeline.py
```
