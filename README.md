# Automated FP&A Variance & Value-Driver Analysis

> An end-to-end, Python-based FP&A analytics pipeline that automates the monthly close review: it builds a multi-version P&L (Actual, Budget, Rolling Forecast v1–v3), quantifies Actual-vs-Budget variances, decomposes revenue variance into price and volume drivers, flags statistically abnormal movements, and surfaces the results in a management dashboard.

## 1. Business Problem

In most of the FP&A teams, the monthly variance review is manual: analysts export ledgers, rebuild the P&L in Excel, compare it to the budget line by line, and then spend most of the cycle explaining *why* the numbers moved. This is slow, error-prone, and the commentary is often inconsistent from month to month.

This project automates that workflow so the analyst's time goes into judgement, not reconciliation:

```
Financial variance  →  Materiality screen  →  Business driver  →  Anomaly / persistence  →  Management insight
```
## 2. Scope

| Dimension      | In scope                                                                  |
|----------------|---------------------------------------------------------------------------|
| Scenarios      | Actual, Budget, Rolling Forecast v1 / v2 / v3                             |
| Time horizon   | Monthly, Jan 2024 – Dec 2026 (36 periods)                                 |
| Organization   | 4 regions (North America, Europe, APAC, Other)                            |
| Products       | 4 products (Alpha, Beta, Gamma, Delta)                                    |
| P&L lines      | Revenue, COGS, Gross Profit, Payroll, Marketing, IT, Travel, OpEx, EBITDA |
| Operational KPIs | Volume, average selling price, discount, customer count                 |

**Out of scope (current version):** balance sheet and cash flow, FX translation, inter-company eliminations, headcount-level payroll planning.

> **Data note:** all data is synthetic and produced by `code/generate.ipynb` with a fixed random seed (42). Business scenarios (volume shortfall in EU for Alpha, price uplift in NAM for Beta, cost inflation in Q2 2026) are injected deliberately so the analytics have known “ground truth” to detect.

## Current Status

- Sprint 1 — Generate Data Foundation    (done)
- Sprint 2 — Build Financial Engine      (done)
- Sprint 3 — Build Variance Engine       (done)
- Sprint 4 — Driver Analysis             (done)
- Sprint 5 — Persistence Analytics       (done)
- Sprint 6 — Dashboard                   (done)
