# Facebook vs AdWords — A/B Testing Analysis

A data-driven analysis of two advertising campaigns (Facebook & AdWords) to determine which platform delivers better ROI in terms of clicks, conversions, and cost-effectiveness.

---

## Business Problem

A marketing agency needs to decide where to allocate its advertising budget — **Facebook Ads** or **Google AdWords**. Using 365 days of campaign data from 2019, this project identifies the more effective platform through statistical analysis and machine learning.

> **Research Question:** Which ad platform is more effective in terms of conversions, clicks, and overall cost-effectiveness?

---

## Dataset

| Feature | Description |
|---|---|
| Date | Jan 1, 2019 – Dec 31, 2019 (365 rows) |
| Ad Views | Number of times the ad was seen |
| Ad Clicks | Number of clicks on the ad |
| Ad Conversions | Number of purchases/actions after clicking |
| Cost per Ad | Daily cost of running the campaign |
| CTR | Click-Through Rate = Clicks ÷ Views |
| Conversion Rate | Conversions ÷ Clicks |
| CPC | Cost Per Click = Ad Cost ÷ Clicks |

---

## Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightgrey)
![Scipy](https://img.shields.io/badge/Scipy-Statistics-orange)
![Sklearn](https://img.shields.io/badge/Sklearn-ML-green)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-9cf)

```
pandas · numpy · matplotlib · seaborn · scipy · sklearn · statsmodels
```

---

## Analysis Overview

### 1. Exploratory Data Analysis (EDA)
- Distribution of clicks and conversions via histograms
- Conversion category frequency comparison (less than 6 / 6–10 / 10–15 / 15+)
- Both platforms showed roughly symmetrical distributions — no major outliers

### 2. Correlation Analysis
- **Facebook:** Clicks vs Conversions correlation = **0.87** (strong positive)
- **AdWords:** Clicks vs Conversions correlation = **0.45** (moderate positive)
- Facebook clicks are a much stronger predictor of conversions

### 3. Hypothesis Testing (Welch's T-Test)
- **H0:** No difference in conversions between Facebook and AdWords
- **H1:** Facebook generates more conversions than AdWords

| Metric | Facebook | AdWords |
|---|---|---|
| Mean Conversions/day | 11.74 | 5.98 |
| T-Statistic | 32.88 | — |
| P-Value | 9.35e-134 | — |
| Result | **Reject H0** | — |

> Facebook delivers statistically significantly more conversions (p << 0.05)

### 4. Linear Regression
- Predicted Facebook conversions based on number of clicks
- **R² Score: 76.35%** — clicks explain 76% of variation in conversions
- For 50 clicks → ~5.9 expected conversions
- For 80 clicks → ~8.8 expected conversions

### 5. Time-Series Analysis
- **Best days:** Monday & Tuesday (highest weekly conversions)
- **Best months (low CPC):** May & November
- **Worst month (high CPC):** February
- **Cointegration test** confirmed a long-term stable relationship between ad spend and conversions

---

## Key Findings

- Facebook generates **~2x more conversions** per day than AdWords
- Facebook clicks are a **strong predictor** of conversions (r = 0.87)
- The difference is **statistically significant** — not due to random chance
- **May & November** are the most cost-effective months to advertise on Facebook
- Ad spend and conversions have a **long-term equilibrium** relationship

---

## Recommendation

> Allocate the majority of the advertising budget to **Facebook Ads**, particularly on **Mondays and Tuesdays** during **May and November** for maximum ROI.

---

## Project Structure

```
facebook-vs-adwords-ab-test/
│
├── facebook_vs_adwords_ab_analysis.ipynb   # Main analysis notebook
├── marketing_campaign.csv                  # Dataset
├── README.md
└── LICENSE
```

---

## How to Run

```bash
# Clone the repo
git clone https://github.com/aditya-datahub/facebook-vs-adwords-ab-test.git

# Install dependencies
pip install pandas numpy matplotlib seaborn scipy scikit-learn statsmodels

# Open the notebook
jupyter notebook facebook_vs_adwords_ab_analysis.ipynb
```

---

## Connect

**Aditya Sharma** — [GitHub](https://github.com/aditya-datahub) · [LinkedIn](https://linkedin.com/in/)
