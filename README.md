# Trader Behavior vs Bitcoin Market Sentiment  
Author: Jayanth

## Overview
This project analyzes how trader behavior on Hyperliquid changes with Bitcoin market sentiment (Fear, Neutral, Greed).  
Two datasets were used:

- Hyperliquid historical trades  
- Bitcoin Fear & Greed Index  

The goal is to understand how sentiment affects trade size, volume, win rate, and profitability.

All work was completed in a single Google Colab notebook.

---

## Folder Structure

ds_jayanth/  
├── notebook.ipynb  
├── csv_files/  
│   ├── hyperliquid_raw.csv  
│   ├── fear_greed_raw.csv  
│   ├── trades_clean.csv  
│   ├── sentiment_clean.csv  
│   └── merged_trades_sentiment.csv  
├── outputs/  
│   ├── avg_pnl_by_sentiment.png  
│   ├── win_rate_by_sentiment.png  
│   ├── avg_notional_by_sentiment.png  
│   ├── total_volume_by_sentiment.png  
│   └── buy_vs_sell_by_sentiment.png  
├── ds_report.pdf  
└── README.md

---

## Data Used

### Hyperliquid Trades Dataset  
Important fields:
- account  
- coin  
- execution_price  
- size_usd  
- side  
- timestamp_ist  
- closed_pnl  

Engineered fields:
- date  
- notional_usd  
- is_profitable  
- direction_num  
- risk_exposure  

### Fear & Greed Index  
Fields:
- date  
- value  
- classification  

Mapped into 3 groups:
- Fear  
- Neutral  
- Greed  

---

## Steps Performed

1. Loaded and cleaned both datasets  
2. Engineered new features  
3. Merged trades with sentiment using the date  
4. Calculated metrics such as:
   - average PnL  
   - win rate  
   - average trade size  
   - total volume  
5. Created visualizations and saved them to the outputs folder  
6. Generated final PDF report

---

## Key Insights

- Greed days have the highest win rate and average PnL  
- Fear days have the largest trade sizes and highest total volume  
- Neutral days show the lowest activity and lowest performance  
- BUY and SELL behavior changes significantly with sentiment  

---

## How to Run

1. Open notebook.ipynb in Google Colab  
2. Upload raw CSVs into the `csv_files` folder  
3. Run all cells  
4. Check outputs/ for charts  
5. Read final insights in ds_report.pdf

---

## Requirements

- Python  
- pandas  
- numpy  
- matplotlib  
- seaborn  

(All available in Google Colab)

---


