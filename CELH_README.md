# Celsius Holdings (CELH) — Equity Valuation

A personal equity-research project: a full **DCF + comparable companies** valuation of Celsius
Holdings (Nasdaq: CELH), the energy-drink maker behind CELSIUS, Alani Nu, and Rockstar. Python
pulls the financials; an Excel model turns them into an intrinsic value and a buy/hold/sell
call.

**The question:** Celsius was one of the best-performing stocks of the decade, then fell
~50%+ from its highs. Is it now a bargain, or still priced for perfection? This project builds
a valuation from scratch to find out — the way an analyst would pitch the stock.

---

## What's in here

| File | What it is |
|------|-----------|
| `CELH_Valuation_Model.xlsx` | The model: DCF, comps, sensitivity, and a summary with a valuation range |
| `CELH_Data_Pull.ipynb` | Python (yfinance) that pulls live financials to refresh the model's inputs |
| `RESULTS.md` | The write-up: the recommendation, the bull/bear case, and the numbers |

---

## How to use it

1. **Pull the data:** open `CELH_Data_Pull.ipynb` in Google Colab → Run all. It prints current
   price, share count, debt, revenue, and peer multiples.
2. **Update the model:** open `CELH_Valuation_Model.xlsx`, go to the **Inputs** tab, and type
   the latest numbers into the blue cells.
3. **Read the answer:** the **Summary** tab recomputes the intrinsic value, the valuation
   range, and the recommendation.

Everything is formula-driven, so changing one assumption flows through the whole model.

---

## How the valuation works

Two independent approaches, cross-checked:

**Discounted Cash Flow (DCF).** Project five years of revenue, margins, and free cash flow,
discount them back at the company's cost of capital (WACC), add a terminal value, and divide
by shares to get an intrinsic value per share. A sensitivity table shows how that value swings
with WACC and long-term growth — because those two assumptions drive everything.

**Comparable Companies.** Value Celsius against beverage peers (Monster, Keurig Dr Pepper,
Coca-Cola, PepsiCo) using EV/EBITDA and P/E multiples. *(EV/Revenue is shown but excluded —
Celsius runs much thinner margins than peers, so a revenue multiple overstates its value. That
adjustment is part of doing comps properly.)*

The two methods are blended into a single target, compared to the current price, and turned
into a recommendation.

---

## Key terms

| Term | Plain meaning |
|------|---------------|
| **DCF** | Valuing a company by its future cash flows, discounted to today |
| **WACC** | The blended rate used to discount those cash flows (the "hurdle rate") |
| **Terminal value** | The value of all cash flows beyond the forecast window |
| **EV/EBITDA** | Enterprise value relative to operating earnings — a core valuation multiple |
| **Comps** | Valuing a company by what similar companies trade for |
| **Margin of safety** | Buying meaningfully below intrinsic value to cushion against being wrong |

---

## Built with

Python (yfinance, pandas) for data · Excel (openpyxl-generated, fully formula-driven) for the model.

---

## Disclaimer

Personal research and educational project. Not investment advice or a recommendation to buy or
sell any security. Figures are point-in-time and should be refreshed before use.
