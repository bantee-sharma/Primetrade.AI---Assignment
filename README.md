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


## 📊 Analysis Performed

**✅ PnL Summary by Sentiment**
Calculated and visualized how average profit/loss varies by sentiment (Fear, Greed, etc.)


**✅ Leverage Analysis**
Observed that leverage stays near 1× (low risk), but spikes during Greed (up to 1.86×), indicating higher risk appetite.

**✅ Buy vs Sell Behavior**
More Sell trades during Fear, likely due to panic selling

More Buy activity in Greed, showing optimism


## 📈 Visualizations

**Plot	Insight**

📊 Bar Plot** – Avg PnL by Sentiment	Traders are more profitable in Extreme Greed

📦 Box Plot** – Leverage Distribution	More risk-taking in Greed

📉 Count Plot** – Buy/Sell Side by Sentiment	Selling dominates in Fear

📈 Line Plot** – Daily Avg PnL	Shows market PnL trends over time



## 💡 Key Insights

Traders are more profitable during Extreme Greed, but also take higher risks

Leverage use increases during Greed, showing aggressive trading

Fear sentiment triggers more Sell trades, indicating market panic

Some coins consistently outperform in Fear or Greed — use this for dynamic portfolio allocation


## 🧾 Strategic Recommendations

**Strategy	Why It Helps**

📉 Lower Leverage in Fear	Reduces risk during market uncertainty

📈 Use Sentiment-Specific Coin Sets	Some coins perform better in Greed, others in Fear

⏳ Lock in Profits in Greed	Prevents loss of gains when sentiment reverses

🧠 Combine Sentiment Signals with Trade Behavior	For smarter entry/exit decisions
