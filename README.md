# Options Trade Analyzer using Polygon.io API

This project is a real-time options screening and enrichment engine built using the **Polygon.io API**. It combines **options chain parsing, IV (Implied Volatility) signals, Monte Carlo simulations, and custom trade tagging** to help identify potentially profitable option trades.

---

## 📈 What It Does

- Screens options contracts across tickers like **AAPL, META, TSLA, GME**, and others
- Calculates key metrics: **breakeven**, **ROI**, **delta**, **theta decay**, **probability ITM**
- Tags trade setups with strategy flags:
  - 🧨 Gamma Spike  
  - 🪙 Micro-Bet  
  - 🏦 Synthetic Long/Short  
  - 🎯 Straddle Candidate
- Uses **Monte Carlo simulations** to simulate spot price distributions and expected P&L
- Ranks and summarizes trades using **LLM-assisted scoring**

---

## 🔧 Tools & Libraries Used

| Tool/Library | Purpose |
|--------------|---------|
| **Polygon.io API** | Real-time stock and option chain data |
| `numpy`, `pandas` | Data transformation and modeling |
| `scipy.stats` | Probabilistic calculations and simulations |
| `matplotlib`, `plotly` | Charting and P&L visualization |
| `OpenRouter LLM API` | Natural language trade summaries |
| Custom `simulate_target()` | Black-Scholes d2-style probability modeling |
| Custom `analyze_positions_with_max_pain()` | Tags & filters option strategies |
| Caching logic | Avoids redundant API calls and supports freshness checks

---

## 🚀 How to Use

1. Add your **Polygon.io API key** securely to your environment.
2. Set your desired tickers and filters (expiry range, IV threshold, delta range).
3. Run the notebook to:
   - Fetch and enrich chain data
   - Simulate trade paths
   - Score trades and generate summaries

---

## 🖼️ Payoff Heatmap Visualizations

These charts simulate P/L outcomes based on spot price movement over time. Each heatmap overlays:

- Target Price Path (Monte Carlo)
- Break-even Point
- Spot Price
- Max Pain

#### 🧪 Example – HOOD $52C
![01_payoff](https://github.com/user-attachments/assets/257c99d7-312f-4627-b27e-b7e70c8abf51)

#### 🧪 Example – NVDA $115C
![02_payoff](https://github.com/user-attachments/assets/9f4cbca5-fcc1-49f1-bf2c-597d1b73d325)

#### 🧪 Example – NVDA $114C (Later Expiry)
![03_payoff](https://github.com/user-attachments/assets/763dff37-9dca-4a51-9750-78f59ce725d5)

#### 🧪 Example – HOOD $55C (Longer-Dated)
![04_payoff](https://github.com/user-attachments/assets/8fd07a98-078e-4270-9c34-1d2c16370a16)

---

## 🧪 Why These Models?

- **Monte Carlo Simulation** is used to simulate price paths and estimate the **probability of a trade ending ITM** based on volatility and time to expiry.
- **Delta and Theta** are extracted or estimated to evaluate directional bias and decay risk.
- **Strategy tagging** helps filter trades by use case (hedge vs lotto vs income).
- **LLM summarization** converts raw analytics into actionable natural language recaps.

---

## 📎 Related Projects

- [Polygon.io Documentation](https://polygon.io/docs)
- [My Options Screener with Strategy Tags](https://github.com/zacharyallen66/options-trade-analyzer)

---

## 📫 Contact

Created by **Zachary Allen**  
📧 zachary.allen@unlv.edu  
🔗 [@zacharyallen66](https://github.com/zacharyallen66)
