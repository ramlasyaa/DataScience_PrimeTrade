# Primetrade.ai - Data Science Intern Assignment Report
**Candidate**: Ram Lasya

## 1. Methodology & Data Preparation
- **Datasets Merged**: Bitcoin Market Sentiment (2616 rows) and Hyperliquid historical trader data (174,668 rows).
- **Alignment**: Parsed the execution timestamps from Hyperliquid (`%d-%m-%Y %H:%M`) and truncated them to daily granularity to merge seamlessly with the sentiment data.
- **Key Metrics Generated**: For each trader on each active day, we aggregated:
  - `daily_pnl`: Sum of `Closed PnL`.
  - `win_rate`: Percentage of winning trades (PnL > 0) out of total trades executed that day.
  - `avg_trade_size`: Mean execution size in USD.
  - `trade_count`: Total number of trades executed that day.

## 2. Key Insights
#### A. Performance Differences: Fear vs. Greed
Analysis reveals that average daily profitability actually **peaks during Fear days** ($5,185 avg PnL vs $4,144 during Greed days). Interestingly, the win rate stays relatively stable across all sentiments (~35-36%), implying that the outperformance during Fear is strictly driven by the magnitude of profitable trades rather than the frequency of winning.

#### B. Behavioral Changes Based on Sentiment
Traders distinctly change their behaviors based on sentiment:
- **Trade Volume and Size**: During Fear days, the average trade size spikes to ~$8,529 (compared to ~$5,954 during Greed) and the frequency of trades increases from ~76 trades/day to ~105 trades/day.
- **Interpretation**: Increased market panic seems to compel traders to take more aggressive positions, either trying to aggressively buy "bottoms" or short volatility.

#### C. Trader Segments (Activity Level)
We segmented users into **Frequent vs. Infrequent Traders** based on their median number of total trades historically.
- **Frequent Traders** excel predominantly during Fear days ($5,968 PnL vs $3,846 on Greed days).
- **Infrequent Traders** perform significantly worse during Fear ($3,090 PnL) but achieve their highest returns during Greed days ($4,987 PnL).

## 3. Actionable Strategy Recommendations (Rules of Thumb)

Based on the empirical evidence from Hyperliquid historicals, we propose the following rules for algorithmic execution or trader alerts:

1. **"The Volatility Filter Rule"**:
   *If a trading account is classified as 'Infrequent' (e.g., executing less than X trades/month), send an alert to lower position sizes by 20-30% during 'Fear' market environments.* Infrequent traders perform worst during fear; they should reduce exposure to volatility and deploy capital primarily during 'Greed' (trend-following) days.

2. **"The Fear Momentum Scaling Rule"**: 
   *For 'Frequent' traders (or high-frequency algorithms), dynamically increase size and execution frequency during 'Fear' conditions.* The data suggests that aggressive capitalization on short-term volatility during Fear days yields the highest expected value (PnL/trade), largely outperforming their Greed day baseline. Systems should relax frequency limits during fear shocks.
