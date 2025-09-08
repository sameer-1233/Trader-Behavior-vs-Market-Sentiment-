# 📊 Trader Behavior vs Market Sentiment Analysis  

## 📌 Project Overview  
This project explores the relationship between **trader behavior** and **market sentiment** (Fear vs. Greed) using two datasets:  

1. **Bitcoin Market Sentiment Dataset**  
   - Columns: `Date`, `Classification` (Fear, Greed, Neutral, Extreme Fear, Extreme Greed).  

2. **Historical Trader Data from Hyperliquid**  
   - Columns: `account`, `symbol`, `execution price`, `size`, `side`, `time`, `start position`, `event`, `closedPnL`, `leverage`, etc.  

The objective was to uncover whether **trading activity and profitability align with overall market sentiment**, and to identify hidden patterns that could inform **smarter trading strategies**.  

---

---

## ⚙️ Methodology  

### 1. Data Preparation  
- Loaded both datasets into Colab.  
- Converted timestamps to datetime, aligned daily frequencies.  
- Checked for missing values (none found).  
- Merged sentiment with trader activity data.  

### 2. Exploratory Data Analysis (EDA)  
- Daily trade counts, average leverage, and average PnL.  
- Visualized trading activity vs sentiment states.  

### 3. Hypothesis Testing  
- **ANOVA tests** were conducted to check if differences exist across sentiment groups:  
  - `Num_Trades` → Significant differences (p < 0.001).  
  - `Size USD` → Significant differences (p < 0.001).  
  - `Closed PnL` → No significant differences.  

- **Tukey HSD post-hoc tests** identified which sentiment groups differ:  
  - **Extreme Fear < Fear < Greed/Extreme Greed** in terms of activity and volume.  
  - Profitability remained unchanged across sentiments.  

### 4. Visualization  
- Bar plots with error bars showing how `Num_Trades` and `Size USD` vary across sentiment categories.  
- Distribution plots of PnL across different sentiment states.  

### 5. Conclusion & Insights  
- **Behavioral Patterns:**  
  - Traders scale back in **Extreme Fear**, and increase trading activity in **Extreme Greed**.  
  - Neutral and mild fear states show minimal differences.  

- **Profitability:**  
  - No meaningful difference in PnL across sentiments → traders act emotionally, not profit-optimally.  

- **Implications:**  
  - Exchanges can anticipate **low activity in Extreme Fear** and adjust incentives.  
  - Risk management is critical in **Extreme Greed** phases where volumes surge.  
  - Traders should be cautious of **overtrading in Greed phases**.  

---

## 🚀 Tools & Libraries Used  
- **Google Colab**  
- Python: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy.stats`, `statsmodels`  

---

## 📌 Final Deliverables  
- **Colab Notebook** with full step-by-step code and explanations.  
- **PDF Report (`ds_report.pdf`)** with summarized findings.  
- **Visualizations** stored under `/outputs`.  
- **README.md** (this file) documenting project setup and insights.  

---

## 📝 Author  
Candidate: `<Your Name>`  
This project was completed as part of the **Data Science hiring assignment** for a Web3 trading team.  
