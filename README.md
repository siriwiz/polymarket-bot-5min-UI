# PolyMarket Bot Wizard

A desktop trading workstation for **5-minute Up/Down markets** on Polymarket.
Built for high-speed decision loops with configurable models, strict risk controls, and clear execution telemetry.

<img width="1919" height="1032" alt="Screenshot 2026-02-24 231449" src="https://github.com/user-attachments/assets/e4151497-ada0-4efd-b382-1657c61d073a" />

## Overview

PolyMarket Bot Wizard combines strategy research and real-time execution in one interface.
You can test logic safely in `PAPER` mode, then deploy the same workflow in `LIVE` mode with market-aware gates.

Core objective:
- Detect short-horizon pricing inefficiencies
- Execute only when edge and liquidity conditions are valid
- Control downside with event/session risk limits

## How It Works

1. Market Data Intake  
   Streams orderbook, trades, and symbol-specific 5-minute window context.

2. Model Evaluation  
   Computes fair value / edge using selected model mode (e.g. Black-Scholes Binary, Queue-Reactive, DOFI+Hawkes).

3. Signal & Filters  
   Applies entry/exit thresholds, calibration filters, SPRT confirmation, Kelly sizing, and timing rules.

4. Risk Gate  
   Verifies spread, top-of-book depth, per-event drawdown, and session loss constraints before any order action.

5. Execution & Monitoring  
   Routes orders (paper sim or live), tracks positions, logs decisions, and updates latency/equity telemetry in real time.

## Features

### Trading Modes
- `PAPER` simulation with realistic orderbook-based fill logic
- `LIVE` execution path via Polymarket CLOB integration

### Strategy Modes
- Black-Scholes Binary
- Queue-Reactive / Microprice
- Non-parametric / ML Calibration
- DOFI + Hawkes + Risk Gate
- PDE / Finite Difference
- Discrete-time Trees
- Stochastic Vol (Heston/SABR)
- Local Vol / Implied Surface
- Bachelier
- Spread Scalping
- Orderbook Mean Reversion
- Momentum / Micro-trend style logic

### Advanced Controls
- Meta-labeling gate
- Online calibration (`None`, `Platt`, `Isotonic`)
- SPRT confirmation
- Kelly sizing with cap
- Time-of-window rules (entry cutoff, force exit, min hold)
- Partial take profit

### Risk Management
- Separate risk profiles for `PAPER` and `LIVE`
- Stop-after-loss at event level
- Max loss per event
- Max session drawdown
- Max spread filter
- Minimum top-of-book size filter
- Cooldown and max entries per window

### Operator UX
- Strategy Control panel
- Live 5-minute market panel
- Orderbook + trade tape
- Positions panel (paper/live)
- Execution logs
- Telemetry (latency, equity, status)
- Optional Liquid Glass visual theme

## Tech Stack

- Electron
- React + Vite
- Node.js engine
- `@polymarket/clob-client`
- `keytar`

## Safety Notice

- `LIVE` mode uses real capital and carries financial risk.
- Start with `PAPER`, validate behavior, then scale carefully.
- This software is a tooling platform, not financial advice.

Contact me https://t.me/siriwiz
