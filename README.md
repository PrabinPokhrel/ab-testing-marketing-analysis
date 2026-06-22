# Marketing Campaign A/B Testing and Conversion Analysis

Statistical analysis of a real-world marketing A/B test using Python,
hypothesis testing, and Power BI — with an auto-generated Excel business report.

## Business Problem

A marketing team ran two campaign variants:
- **Ad group (Test):** Users shown a paid advertisement
- **PSA group (Control):** Users shown a public service announcement

The goal is to determine whether the ad campaign significantly improves
conversion rate and whether it is worth deploying at scale.

## Key Results

| Metric | Value |
|--------|-------|
| Total users | 588,101 |
| Ad group users | 564,577 |
| PSA group users | 23,524 |
| Ad conversion rate | 2.5547% |
| PSA conversion rate | 1.7854% |
| Absolute uplift | +0.7692 percentage points |
| Relative uplift | +43.09% |
| Z-statistic | 7.37 |
| P-value | < 0.0001 |
| 95% Confidence Interval | [0.5951%, 0.9434%] |
| Cohen's h | 0.0530 (Small effect) |
| Statistically significant | YES |

## Recommendation

**Deploy the ad campaign.** The test provides overwhelming statistical
evidence (p < 0.0001, Z = 7.37) that the ad group converts at a
significantly higher rate than the PSA control. The 95% confidence
interval lies entirely above zero, confirming the ad's positive impact
across all plausible scenarios.

While Cohen's h = 0.053 indicates a small practical effect — common
with very large samples — the 43% relative uplift translates to
approximately 385 additional conversions per 50,000 monthly users.
Monday and Tuesday show the highest conversion uplift and should be
prioritised for ad delivery.

## Key Findings

- Ad group converts at 2.55% vs PSA at 1.79% — a 43% relative uplift
- Both Chi-square (54.0) and Z-test (7.37) confirm statistical significance
- Effect is statistically large but practically small (Cohen's h = 0.053)
  — a nuance that distinguishes rigorous analysis from surface-level reporting
- Monday has the highest conversion for both groups (Ad: 3.31%, PSA: 2.26%)
- Conversion peaks between 4pm and 5pm for both groups
- PSA group has near-zero conversions between midnight and 6am due to
  small sample size at those hours

## Tech Stack

- Python: Pandas, NumPy, SciPy, Statsmodels, Matplotlib, Seaborn, OpenPyXL
- Statistical methods: Chi-square test, Two-proportion Z-test, Cohen's h,
  Power analysis, Confidence intervals
- Reporting: Auto-generated Excel report with 3 formatted sheets
- Visualisation: Power BI dashboard

## Project Structure
ab-testing-marketing-analysis/

├── data/                          # Output charts and CSV results

├── notebooks/

│   ├── 01_eda.ipynb               # Exploratory data analysis

│   ├── 02_hypothesis_testing.ipynb # Statistical tests and effect size

│   └── 03_excel_report.ipynb      # Auto-generated Excel report

├── outputs/

│   └── ab_test_report.xlsx        # Final Excel business report

├── dashboard/

│   └── ab_test_dashboard.pbix     # Power BI dashboard

└── requirements.txt

## Dataset

Marketing A/B Testing Dataset — publicly available on Kaggle:
https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing

588,101 users split into ad and PSA groups with conversion tracking.

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook
```

Run notebooks in order: 01 → 02 → 03
