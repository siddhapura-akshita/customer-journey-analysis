# Customer Journey Analysis

End-to-end analytics pipeline that transforms raw clickstream data into actionable e-commerce insights. Built in Python, designed to run cell-by-cell in VS Code.

## What It Does

**Basic Analysis** (`customer_journey_analysis.py`)
- Data cleaning, funnel mapping, session metrics, user segmentation (Browser / Cart Abandoner / Buyer), and conversion visualizations.

**Advanced Analysis** (`advanced_customer_journey.py`)
- Markov chain transition probabilities & absorption rates
- Temporal conversion patterns (hourly, daily, monthly heatmaps)
- Monthly cohort retention analysis
- Weighted engagement scoring model (Cold → Power User tiers)
- Purchase prediction with Logistic Regression & Random Forest (ROC, feature importance, confusion matrix)
- Chi-square & Mann-Whitney U statistical significance tests with effect sizes
- RFM segmentation (Champions → Hibernating)
- Cart abandonment deep-dive by device, referral, and cart size
- Cross-dimensional conversion heatmaps (Device × Referral × Country)
- Feature correlation matrix

## Key Findings

| Metric | Value |
|---|---|
| Overall funnel conversion | 42.3% |
| Biggest drop-off | Product View → Cart (38.5%) |
| Cart abandonment rate | 36.8% |
| Peak conversion hour | 15:00 |
| Top predictive features | Funnel depth, unique pages visited |

## Setup

```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

```
project/
├── data/
│   └── customer_journey.csv
├── customer_journey_analysis.py
├── advanced_customer_journey.py
├── outputs/                  # basic analysis exports
    └── outputs_advanced/     # advanced analysis exports
```

Place the dataset in `data/`, then run either script. Both use `# %%` cell markers for interactive execution in VS Code.

## Dataset

12,719 clickstream events across 5,000 sessions from 1,872 users (Jan–Aug 2025). Columns: `SessionID`, `UserID`, `Timestamp`, `PageType`, `DeviceType`, `Country`, `ReferralSource`, `TimeOnPage_seconds`, `ItemsInCart`, `Purchased`.

## Outputs

Each script auto-generates charts (`.png`) into its output folder — funnel charts, heatmaps, ROC curves, segment distributions, and more.

## Tech Stack

Python · Pandas · NumPy · Matplotlib · Seaborn · Scikit-learn · SciPy
