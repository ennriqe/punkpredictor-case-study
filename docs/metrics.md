# Metrics Snapshot Notes (Public / Sanitized)

## Important Context

Metrics change over time as new sales complete and additional prediction/sale pairs become eligible for evaluation.

This case study uses:
- **CV-aligned summary metrics (Feb 2026)** for headline communication
- a **representative internal snapshot exported on 2026-02-09** (sanitized summary below) to illustrate the evaluation format

## CV-Aligned Headline Metrics (Feb 2026)

### Valuation quality
- 2,807 sales
- MAPE 6.92%
- Median APE 4.68%
- Signed bias -0.80%

### Strategy-style evaluation (forward/live predictions)
- Sharpe 2.23 vs 1.57 passive baseline
- Max drawdown 16.32% vs 41.02% passive baseline

## Example Public Metrics Snapshot (2026-02-09)

Representative values from a point-in-time snapshot (rounded):

- Raw performance records: 2,787
- Prediction/completed-sale pairs: 784
- Buy-all completed-sale pairs: 1,296
- Filtered out pairs: 512
- Floor series coverage: 2017-06-23 to 2026-02-09

### Risk metrics (prediction strategy)
- Sharpe: 2.28
- Sortino: 11.75
- Calmar: 7.70
- Max drawdown: 16.32%

### Risk metrics (buy-all baseline)
- Sharpe: 1.63
- Sortino: 4.76
- Calmar: 3.21
- Max drawdown: 39.00%

## Interpretation

The exact values drift as the evaluation window extends, but the evaluation framework is the key point:
- forward/live prediction tracking
- benchmark comparison
- risk-adjusted metrics, not just hit rate or raw P&L
- transparent handling of filtered/eligible pairs
