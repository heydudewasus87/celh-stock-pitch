# Celsius Holdings (CELH) — Equity Valuation

A full **DCF + comparable companies** valuation of Celsius
Holdings (Nasdaq: CELH), the energy-drink maker behind CELSIUS, Alani Nu, and Rockstar. Python
pulls the financials from Yahoo Finance and an Excel model turns them into an intrinsic value and a buy/hold/sell
call.

**The question:** Celsius was one of the best-performing stocks of the decade, then fell
~50%+ from its highs. Is it now a bargain, or still priced for perfection? This project builds
a valuation from scratch.

---

## What's in here

| File | What it is |
|------|-----------|
| `CELH_Valuation_Model.xlsx` | The model: DCF, comps, sensitivity, and a summary with a valuation range |
| `CELH_Data_Pull.ipynb` | Python (yfinance) that pulls live financials to refresh the model's inputs |
| `RESULTS.md` | The write-up: the recommendation, the bull/bear case, and the numbers |

---

## How the valuation works

Two independent approaches, cross-checked:

**Discounted Cash Flow (DCF).** Project five years of revenue, margins, and free cash flow,
discount them back at the company's cost of capital (WACC), add a terminal value, and divide
by shares to get an intrinsic value per share. A sensitivity table shows how that value swings
with WACC and long-term growth because those two assumptions drive everything.

**Comparable Companies.** Value Celsius against beverage peers (Monster, Keurig Dr Pepper,
Coca-Cola, PepsiCo) using EV/EBITDA and P/E multiples. *(EV/Revenue is shown but excluded as
Celsius runs much thinner margins than peers, so a revenue multiple overstates its value. That
adjustment is part of doing comps properly.)*

The two methods are blended into a single target, compared to the current price, and turned
into a recommendation.


---

## Built with

Python (yfinance, pandas) for data · Excel (openpyxl-generated, fully formula-driven) for the model.

---

## Disclaimer

Personal research and educational project. Not investment advice or a recommendation to buy or
sell any security. Figures are point-in-time and should be refreshed before use.
