# polymarket-bot-5min-UI

diff --git a/f:\Bot\pm-bot\README.md b/f:\Bot\pm-bot\README.md
new file mode 100644
--- /dev/null
+++ b/f:\Bot\pm-bot\README.md
@@ -0,0 +1,121 @@
+# PolyMarket Bot Wizard
+
+An Electron + React desktop app for trading **5-minute Up/Down markets** with configurable strategy logic, risk controls, and real-time execution telemetry.
+
+Built for fast iteration in `PAPER` mode and controlled deployment in `LIVE` mode.
+
+## Why This Project
+
+- Multi-market focus: `BTC`, `ETH`, `SOL`, `XRP`
+- Strategy-first workflow: model switching + granular controls
+- Practical risk tooling: event/session limits, spread and liquidity gates
+- Clean desktop UX: live orderbook/trades/positions/logs in one view
+
+## Core Features
+
+### Trading Modes
+
+- `PAPER` mode for safe strategy testing
+- `LIVE` mode for real order routing via Polymarket CLOB
+
+### Strategy Engine
+
+- Multiple model families, including:
+  - `Black-Scholes Binary`
+  - `Queue-Reactive / Microprice`
+  - `DOFI + Hawkes + Risk Gate`
+  - `Non-parametric / ML calibration`
+  - `PDE / Trees / Stoch Vol / Local Vol / Bachelier`
+  - `Spread Scalping / Mean Reversion / Momentum`
+
+### Advanced Filters
+
+- Meta-label gate (`Meta ON/OFF`)
+- Online calibration (`None / Platt / Isotonic`)
+- Sequential decision control (`SPRT`)
+- Kelly-based position sizing (fractional + max risk cap)
+- Time-of-window controls (`entry cutoff`, `force exit`, `min hold`)
+- Partial take profit controls
+
+### Risk Controls
+
+- Separate `PAPER` and `LIVE` risk profiles
+- Stop-on-loss behavior
+- Max loss per event / per session
+- Orderbook gating: max spread + minimum top-of-book size
+- Cooldown and max entries per window
+
+### Monitoring & Ops
+
+- Execution logs
+- Latency timeline
+- Balance/equity telemetry
+- Live orderbook and trades
+- Positions panel
+- Strategy snapshot + edge pipeline view
+
+## Tech Stack
+
+- **Desktop:** Electron
+- **Frontend:** React + Vite
+- **Engine:** Node.js (`electron/botEngine.cjs`)
+- **Trading:** `@polymarket/clob-client`
+- **Key storage:** `keytar`
+
+- Private keys are handled through the local vault (`keytar` integration).
+- `LIVE` trading involves real financial risk.
+- This project is a beta trading tool, not financial advice.
+
+## Current Status
+
+Actively iterating. Strategy and UI modules are designed for rapid tuning and experimentation.
+
