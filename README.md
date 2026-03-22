# NHS Referral Demand Forecasting

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python&logoColor=white)
![Status](https://img.shields.io/badge/Status-In%20Progress-orange)
![Data](https://img.shields.io/badge/Data-NHS%20England%20Open%20Data-005EB8?logo=nhs)
![Methods](https://img.shields.io/badge/Methods-ARIMA%20%7C%20LSTM%20%7C%20Time%20Series-green)
![Domain](https://img.shields.io/badge/Domain-Healthcare%20Analytics-red)

---

## The Business Question

> **"Can outpatient referral demand be predicted 4–8 weeks ahead to support NHS workforce and capacity planning?"**

Every week, NHS trusts receive thousands of GP referrals for outpatient appointments. Without reliable forecasts, trusts face two costly extremes: overstaffing idle clinics, or underpreparing and leaving patients waiting. A working demand forecast — even a rough one — lets planners schedule staff earlier, reduce waiting times, and identify seasonal surges before they become crises.

This project uses NHS England's publicly available Referral to Treatment (RTT) waiting times data to build a time series forecasting model that predicts weekly referral volumes 4–8 weeks in advance.

---

## Dataset

| Property | Detail |
|---|---|
| **Source** | [NHS England — Referral to Treatment Waiting Times](https://www.england.nhs.uk/statistics/statistical-work-areas/rtt-waiting-times/) |
| **Coverage** | England, all NHS Trusts, by specialty |
| **Granularity** | Weekly, by treatment function code |
| **Format** | CSV (one file per month, combined) |
| **Why this dataset** | It is public, nationally representative, updated weekly, and directly tied to a measurable operational problem |

**Specialty selected:** Trauma & Orthopaedics (treatment function code 110) — highest referral volume specialty in England, significant seasonal variation, and a major source of waiting list pressure.

---

## Approach

### Why ARIMA first?

ARIMA (AutoRegressive Integrated Moving Average) is the standard baseline for univariate time series forecasting. It is interpretable, well understood by NHS analysts, and captures autocorrelation and trend. If ARIMA performs adequately, it wins on simplicity.

### Why LSTM as the challenger?

Long Short-Term Memory networks can capture non-linear patterns and longer-range dependencies — for example, the multi-year referral suppression during COVID-19 followed by a demand surge. ARIMA cannot model this kind of structural break cleanly. LSTM is tested as the challenger to see whether complexity is justified.

### Evaluation metric

Mean Absolute Percentage Error (MAPE) — chosen because it is interpretable by non-technical stakeholders: a MAPE of 8% means forecasts are off by 8% on average.

---

## Key Findings

> *(To be updated once analysis is complete)*

---

## What a Business Would Do With This

An NHS capacity planner with a reliable 4-week referral forecast could:

- **Pre-schedule clinic slots** — book radiographers, surgeons and admin staff weeks in advance rather than reacting to demand
- **Reduce waiting times** — allocate capacity before bottlenecks form rather than after
- **Flag demand surges early** — trigger escalation protocols before backlogs breach 18-week targets
- **Inform workforce contracts** — justify bank/agency spend with data rather than gut feel

---

## Repository Structure

```
nhs-referral-demand-forecasting/
│
├── notebook/
│   └── nhs_referral_demand_forecasting.ipynb   # Main analysis notebook
│
├── data/
│   └── README.md                               # Data download instructions
│
└── README.md
```

---

## Skills Demonstrated

`Python` `Pandas` `statsmodels` `TensorFlow/Keras` `ARIMA` `LSTM` `Time Series Forecasting` `Matplotlib` `Seaborn` `NHS Open Data` `Healthcare Analytics`

---

## Author

**Yenlik Gaisina** | Data Analyst | MPH | Cambridge Data Science & AI  
[LinkedIn](https://www.linkedin.com/in/yenlik-gaisina/) · [Portfolio](https://gaisina.co.uk/portfolio.html)
