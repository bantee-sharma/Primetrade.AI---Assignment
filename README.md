# Primetrade.AI-Assignment

This project analyzes how trader performance varies under different market sentiment conditions (Fear, Greed, etc.) using real-world trade data from the Hyperliquid platform and sentiment data from the Bitcoin Fear & Greed Index.

___


## 🎯 Objective

The goal is to explore the relationship between **trader behavior** and **market sentiment**, and extract **actionable insights** to guide smarter trading decisions.

We focus on:
- Profit/loss trends across different emotions (Fear, Greed, etc.)
- Risk-taking behavior via leverage analysis
- Buy/Sell preferences in different sentiments
- Visualizing behavioral patterns for strategy development

  ---

## 📁 Datasets Used

1. **Fear-Greed Index Dataset**
   - Columns: `timestamp`, `value`, `classification`, `date`
   - Source: Alternative.me API

2. **Hyperliquid Trader Dataset**
   - Columns: `Account`, `Coin`, `Execution Price`, `Size Tokens`, `Size USD`, `Side`, `Timestamp IST`, `Closed PnL`, `Fee`, etc.
   - Over 200,000 trades executed by real traders

---
## 🧹 Data Preprocessing

- Converted all date columns to `datetime`
- Extracted and normalized `date` from `Timestamp IST`
- Merged both datasets on the `date` field
- Engineered a new column:  
  ```python
  Leverage = Size USD / (Size Tokens × Execution Price)
