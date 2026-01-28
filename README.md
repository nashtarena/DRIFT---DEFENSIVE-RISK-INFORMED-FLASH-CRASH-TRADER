# DRIFT - Defensive Risk-Informed Flash-Crash Trader

A crypto trading strategy designed to survive flash crashes while preserving capital.

## What It Does

DRIFT protects your money during crypto crashes. When prices drop fast (like Terra/Luna's 99% crash in 2022), this strategy:
- Detects danger early
- Exits positions before major losses
- Re-enters when safe
- Limits losses to under 10%

## Assets Covered

- Anchor Protocol
- Polygon (MATIC)
- Terra (LUNA)
- Ethereum (ETH)
- Avalanche (AVAX)

## How It Works

**Risk Detection**
- Watches volatility (how much prices jump around)
- Spots when 2+ assets start crashing together
- Uses machine learning to predict crashes

**Protection Rules**
- Maximum loss per asset: -10%
- Maximum portfolio loss: -8%
- Quick exit when danger detected
- Smart re-entry using trend signals

## Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

## Installation

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## Usage

1. Place your CSV files in the project folder:
   - `anchor-protocol.csv`
   - `polygon.csv`
   - `terra-luna.csv`
   - `ethereum.csv`
   - `avalanche.csv`

2. Run the notebook:
   ```bash
   jupyter notebook strategy.ipynb
   ```

## CSV Format

Your data files need these columns:
- `date` - trading date
- `price` - asset price

## Results

**What Worked:**
- Preserved 96-99% of capital during crashes
- Max drawdowns: -1.3% to -3.4% (very small losses)
- Quick recovery (0 days on most assets)
- AVAX: 7.5% growth with controlled risk

**What Needs Work:**
- Too conservative - misses some profit opportunities
- Low trading frequency
- Negative Sharpe ratios on defensive assets

## Key Metrics

- **CSI** (Crash Survival Index) - custom score measuring crash resistance
- **Drawdown** - maximum % loss from peak
- **Recovery Time** - days to recover from losses
- **Sharpe Ratio** - return vs. risk measure (higher is better)

## Future Improvements

- Relax exit rules to capture more profits
- Better crash detection to reduce false alarms
- Optimize for more frequent trading

## Trading Fees

Current fee assumption: 0.1% per trade

## Disclaimer

This is for educational purposes. Past performance doesn't guarantee future results. Crypto trading is risky - only invest what you can afford to lose.
