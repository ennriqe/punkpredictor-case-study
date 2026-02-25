# Evaluation and Promotion Philosophy

## Core Principle

A model is not considered "better" because it scores well on one offline split. The production workflow evaluates contenders through staged checks before they can replace the current champion model.

## Evaluation Layers

### Offline training diagnostics
- training/validation loss curves
- error distributions (MAPE and related metrics)
- scatter diagnostics and run-level summaries
- reproducible run artifacts with metadata

### Model-vs-online comparison
- contender compared against the current champion model
- comparison artifacts generated before promotion decisions
- intended to catch regressions hidden by absolute metrics

### Promotion gates
- threshold-based checks on key metrics and policies
- promotion can be automatic or shadow-first depending on policy configuration

### Post-promotion monitoring
- live behavior monitored after a promotion event
- rollback path exists if live metrics degrade beyond thresholds

## Quant Research Alignment

Model quality is not the only objective. The system also supports risk-adjusted benchmark comparisons (e.g., Sharpe and drawdown versus a passive baseline) using forward/live predictions rather than retroactive signal generation. Public results: [punkpredictor.xyz/backtest](https://punkpredictor.xyz/backtest).
