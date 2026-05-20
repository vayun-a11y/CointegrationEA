# CointegrationEA

A MetaTrader 5 Expert Advisor for multi-pair cointegration spread trading. The EA runs two independent pair systems, updates hedge ratios with a Kalman filter, validates mean reversion, and trades spread entries/exits from z-score thresholds.

## Strategy Overview

- System A: `EURUSDm` / `GBPUSDm`
- System B: `AUDUSDm` / `NZDUSDm`
- Timeframe: H1 by default
- Entry: open spread when absolute z-score exceeds the configured entry threshold
- Exit: close spread when absolute z-score reverts below the configured exit threshold
- Filters: stationarity check, half-life bounds, and ADX regime filter

## Trading Flow

```text
New H1 bar
Update Kalman hedge ratio
Run scheduled cointegration and half-life checks
Check trend regime with ADX
Close positions if filters fail
Calculate current z-score
Open long/short spread on entry threshold
Close spread on exit threshold
```

## Files

```text
coint.mq5   MetaTrader 5 Expert Advisor source
README.md  Project documentation
```

## Installation

1. Open MetaTrader 5.
2. Go to `File > Open Data Folder`.
3. Copy `coint.mq5` into `MQL5/Experts/`.
4. Compile it in MetaEditor.
5. Attach the EA to a chart and configure symbols, lots, thresholds, and magic numbers.

## Risk Notes

This is experimental trading software. Backtest with realistic spreads, commissions, slippage, symbol suffixes, and broker execution rules before running on a live account.
