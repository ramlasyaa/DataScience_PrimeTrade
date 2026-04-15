# Primetrade.ai Data Science Intern - Round 0 Assignment

This repository contains my submission for the Data Science Internship evaluation. The analysis uncovers patterns relating market sentiment (Fear/Greed) to trader behavior and performance on the Hyperliquid platform.

## Repository Contents

*   `data/`: Directory intended for the `sentiment.csv` and `hyperliquid.csv` files.
*   `analysis.ipynb`: The primary Jupyter Notebook containing the data preparation, analysis, metrics formulation, and visualization steps.
*   `report.md`: A 1-page write-up summarizing the methodology, insights, and actionable trading rules.
*   `*.png`: The resulting charts used as evidence to back up our insights.

## Setup and How to Run

1.  **Clone the repository:**
    ```bash
    git clone <repository_url>
    cd primetrade-assignment
    ```

2.  **Add Datasets:**
    Ensure that the two datasets (`sentiment.csv` and the historical trader data renamed to `hyperliquid.csv`) are placed within the `data/` subdirectory.

3.  **Environment Setup:**
    Create a Python virtual environment and install the required dependencies:
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    pip install pandas numpy matplotlib seaborn jupyter
    ```

4.  **Execute Analysis:**
    Launch Jupyter and open the notebook to view or re-run the analysis:
    ```bash
    jupyter notebook analysis.ipynb
    ```
    Alternatively, you can run all cells head-to-tail to reproduce the metrics and charts.

    ---

## 📊 Key Insights

### 🔹 Insight 1: Market Sentiment Impacts Profitability
Traders tend to generate **lower average PnL during Fear periods** compared to Greed periods, indicating cautious or reactive trading behavior.

### 🔹 Insight 2: High Leverage Increases Risk in Fear Markets
High leverage traders show **greater losses during Fear conditions**, suggesting amplified downside risk when market sentiment is negative.

### 🔹 Insight 3: Increased Activity During Greed
Trade frequency significantly **increases during Greed periods**, reflecting more aggressive participation and confidence in the market.

---

## 👥 Trader Segmentation

To better understand behavioral patterns, traders were segmented into:

- **High vs Low Leverage Traders**
- **Frequent vs Infrequent Traders**
- **Consistent Winners vs Inconsistent Traders**

These segments reveal how different trader types respond uniquely to market sentiment.

---

## 💡 Actionable Strategies

### 🚀 Strategy 1: Risk Reduction in Fear Markets
Reduce leverage exposure during Fear periods to minimize potential drawdowns, especially for high-risk traders.

### 🚀 Strategy 2: Selective Aggression in Greed Markets
Increase trading activity during Greed phases, but only for traders with historically consistent performance.

---

## 📎 Resume
[View Resume](https://drive.google.com/file/d/1L8czJ1ncReidYdw3gZpYwDC8sGgrrjB4/view?usp=sharing)
