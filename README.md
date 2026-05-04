# Algorithmic Trading Systems

> Multi-filter institutional-grade algorithmic trading systems built for private clients (2023–2025)

A collection of algorithmic trading system architectures designed and delivered to private clients — incorporating post-earnings data analysis, multi-timeframe technical confirmation, and institutional signal filtering.

---

## Overview

These systems were designed to replicate institutional-grade signal filtering at the retail level — combining fundamental catalysts (earnings, government disclosures) with multi-timeframe technical confirmation to generate high-conviction trade setups.

---

## System Architecture

### Signal Layer
- **Post-Earnings Drift Analysis** — captures systematic price behavior following earnings surprises
- **Government Disclosure Monitoring** — tracks SEC filings, congressional trades, and institutional 13F changes
- **Catalyst Detection** — identifies FDA approvals, contract awards, and regulatory events as entry triggers

### Technical Confirmation Layer
Multi-timeframe confirmation across:
- **RSI** (Relative Strength Index) — momentum and overbought/oversold detection
- **MACD** — trend direction and momentum crossovers
- **Bollinger Bands** — volatility-adjusted entry zones
- **EMA Stacks** — trend alignment across 9/21/50/200 EMA
- **Volume Profile** — institutional accumulation/distribution detection

### Risk Management Layer
- Position sizing based on ATR (Average True Range)
- Hard stop-loss and trailing stop logic
- Maximum drawdown circuit breakers
- Correlation-based portfolio exposure limits

### Execution Layer
- Signal generation → alert delivery pipeline
- Broker API integration (TD Ameritrade, Interactive Brokers)
- Paper trading mode for system validation

---

## Key Design Principles

**Confluence over frequency** — systems only fire when multiple independent signals align, reducing false positives at the cost of trade frequency.

**Asymmetric risk/reward** — minimum 2:1 reward-to-risk ratio enforced at signal generation, not just position sizing.

**Catalyst-driven entries** — technical setups are only acted upon when a fundamental catalyst (earnings, government data, regulatory event) provides a directional thesis.

---

## Technologies

| Component | Technology |
|---|---|
| Data Feeds | Polygon.io, Alpaca, SEC EDGAR, Congressional disclosure APIs |
| Signal Processing | Python, pandas, numpy, ta-lib |
| Backtesting | Backtrader, custom vectorized backtesting engine |
| Execution | Alpaca API, TD Ameritrade thinkorswim API |
| Alerting | Webhook delivery, SMS (Twilio), Discord |
| Infrastructure | Docker, GitHub Actions, scheduled cron pipelines |

---

## Evolution into AlphaPipeline

The government data monitoring and signal processing architecture from these systems directly informed the design of [AlphaPipeline.ai](https://alphapipeline.ai) — a production AI SaaS platform integrating 60+ government data sources with LLM materiality scoring, autonomous paper trading, and real-time signal delivery.

---

## About

Designed and delivered by [Ahmad Albaba](https://github.com/a2sh16) for private clients. Not financial advice. Past performance does not guarantee future results.
