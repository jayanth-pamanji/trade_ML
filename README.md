```markdown
# Trader Behavior vs Bitcoin Market Sentiment  
### Data Science Assignment – Web3 Trading Team  
**Author: Jayanth**

---

## 📌 Project Overview

This project analyzes how **trader behavior** on Hyperliquid changes with **Bitcoin market sentiment** (Fear, Neutral, Greed).  
The study combines two datasets:

- **Hyperliquid Historical Trader Data**  
- **Bitcoin Fear & Greed Index**

The objective is to understand:

- How trade size, volume, and profitability change with sentiment  
- Whether traders perform better during Fear or Greed  
- Behavior patterns that can help build smarter trading and risk-management strategies  

All work was completed in **a single Google Colab notebook** for clean and streamlined workflow.

---

## 📂 Folder Structure

```

ds_jayanth/
├── notebook.ipynb                     # Single notebook containing all work
├── csv_files/
│   ├── hyperliquid_raw.csv            # Raw trades data
│   ├── fear_greed_raw.csv             # Raw sentiment data
│   ├── trades_clean.csv               # Cleaned trades dataset
│   ├── sentiment_clean.csv            # Cleaned sentiment dataset
│   └── merged_trades_sentiment.csv    # Final merged dataset
├── outputs/
│   ├── avg_pnl_by_sentiment.png
│   ├── win_rate_by_sentiment.png
│   ├── avg_notional_by_sentiment.png
│   ├── total_volume_by_sentiment.png
│   ├── buy_vs_sell_by_sentiment.png
│   └── additional charts
├── ds_report.pdf                      # Final insights report
└── README.md

```

---

## 📊 Dataset Details

### **1. Hyperliquid Trades Dataset**
Includes fields:
- account, coin  
- execution_price  
- size_tokens, size_usd  
- side (BUY/SELL)  
- timestamp_ist  
- closed_pnl  
- fee  

### **Engineered Features**
- date  
- notional_usd  
- is_profitable  
- direction_num  
- risk_exposure  

---

### **2. Bitcoin Fear & Greed Index**
Includes:  
- timestamp  
- value (0–100)  
- classification  
- date  

### **Sentiment Groups Used**
- Fear      → Extreme Fear + Fear  
- Neutral   → Neutral  
- Greed     → Greed + Extreme Greed  

Added columns:  
- sentiment_group  
- sentiment_binary  

---

## 🔧 Steps Performed (Single Notebook Workflow)

In a single notebook, the following steps were completed:

### **Data Cleaning**
- Standardized column names  
- Parsed timestamps and extracted date  
- Converted numeric fields  
- Cleaned sentiment classification  
- Mapped sentiment into 3 groups  

### **Feature Engineering**
- Created notional_usd  
- Added is_profitable (pnl > 0)  
- Added direction_num (BUY=1, SELL=−1)  
- Added risk_exposure  

### **Merging**
- Trades merged with sentiment on date  
- Created final dataset for analysis  

### **Analysis & Visualization**
Generated these charts:

- Average PnL by sentiment  
- Win rate by sentiment  
- Average position size  
- Total trading volume  
- BUY vs SELL distribution  

All plots saved to `outputs/`.

### **Saving Files**
- All cleaned CSVs saved into `csv_files/`  
- All charts saved into `outputs/`  

---

## 📈 Key Insights

### **1. Profitability**
- Greed days show the **highest average PnL**  
- Win rate is also highest in Greed  
- Traders perform best during optimistic market sentiment  

### **2. Position Size**
- Fear days show **largest average trade size (~$7,182)**  
- Traders take more aggressive risks during fearful/volatile markets  

### **3. Volume**
- Fear has the **highest total notional (~$598M)**  
- Neutral has the lowest activity  

### **4. BUY vs SELL**
- Fear → BUY ≈ SELL (panic selling + dip buying)  
- Greed → more SELL (profit-taking)  
- Neutral → lowest activity  

