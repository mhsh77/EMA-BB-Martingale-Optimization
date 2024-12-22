# EMA & Bollinger Bands Trading Strategy with Martingale

This repository implements and optimizes a trading strategy based on Exponential Moving Averages (EMA) and Bollinger Bands. The strategy is further enhanced by a Martingale position-sizing approach, which significantly improves profitability over time.

## Strategy Description

The strategy combines technical indicators to determine entry and exit points for trades, using EMA and Bollinger Bands for precise decision-making. Additionally, the Martingale system adjusts position sizes based on previous trade outcomes, helping recover losses and enhance returns.

### Entry Conditions
![bokeh_plot_ema_bb_how_it_works](https://github.com/user-attachments/assets/af6e4908-a00c-493f-b488-9b93d25055e5)

1. **Long Positions:**
   - The 7-period EMA (EMA7) is greater than the 30-period EMA (EMA30).
   - The current price is below the lower Bollinger Band.

2. **Short Positions:**
   - The 7-period EMA (EMA7) is less than the 30-period EMA (EMA30).
   - The current price is above the upper Bollinger Band.

### Exit Conditions
Trades are exited when either the stop-loss or take-profit levels are hit. These levels are optimized for maximizing performance.

### Martingale Position Sizing
- After a **losing trade**, the position size doubles to recover previous losses.
- After a **winning trade**, the position size resets to the base level.

## Performance Results

- **Initial Performance (without Martingale):** -0.09% return.
- ![bb_ema_all_trades](https://github.com/user-attachments/assets/146ad65c-b0b2-4f76-8b75-76763d0612bd)

- **Optimized with Martingale:** +7% return.
- 
![ema_bb_martingale_optimized](https://github.com/user-attachments/assets/aea7020e-d3c5-4991-a395-6cdfbdec03ee)

The Martingale system, coupled with strategic optimization, demonstrates substantial improvements in profitability.

## Implementation Details

### Tools and Libraries
This repository uses the following tools:
- **[Backtest.py](https://kernc.github.io/backtesting.py/):** A lightweight Python library for backtesting trading strategies.
- **[pandas_ta](https://github.com/twopirllc/pandas-ta):** A comprehensive library for technical analysis indicators.

### Key Files
- **`strategy.py`:** Contains the implementation of the EMA & Bollinger Bands strategy with Martingale.
- **`backtest.py`:** Runs the backtesting process using historical data and reports performance results.
- **`data.csv`:** Example dataset for testing the strategy (you can replace this with your own historical data).

## How to Use

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/ema-bollinger-martingale.git
cd ema-bollinger-martingale
```

### 2. Install Dependencies
Make sure you have Python 3.x installed, then install the required libraries:
```bash
pip install -r requirements.txt
```

### 3. Run Backtesting
Execute the backtesting script to test the strategy:
```bash
python backtest.py
```

### 4. Customize Parameters
You can adjust key parameters in the `strategy.py` file, such as:
- Stop-loss and take-profit multipliers.
- Martingale settings.
- Indicator configurations (e.g., EMA periods or Bollinger Band width).

## Example Output
After running the backtesting script, you will see key metrics like:
- Net return
- Number of trades
- Maximum drawdown
- Sharpe ratio

Performance plots are also generated for visual analysis.

## Example Strategy Flow
1. **Detect Signal:**
   - Check if EMA7 crosses above or below EMA30.
   - Confirm if the price is outside Bollinger Bands.

2. **Place Trade:**
   - Determine position size using Martingale logic.
   - Set stop-loss and take-profit levels based on ATR or fixed values.

3. **Optimize and Analyze:**
   - Review performance metrics.
   - Tune parameters for better results.

## Requirements
- Python 3.x
- Libraries:
  - `pandas`
  - `numpy`
  - `matplotlib`
  - `pandas_ta`
  - `backtesting`

Install all dependencies with:
```bash
pip install -r requirements.txt
```

## Limitations
- **Martingale Risk:** While the Martingale approach can recover losses, it increases risk due to exponentially growing position sizes during losing streaks.
- **Data Dependency:** Ensure high-quality historical data for accurate backtesting.

## Disclaimer
This strategy is for educational purposes only. Trading involves significant risk, and past performance is not indicative of future results. Use at your own discretion.

---

Feel free to contribute, report issues, or suggest improvements to this repository!
