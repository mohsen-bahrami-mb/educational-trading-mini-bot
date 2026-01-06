# Mini Trading Bot (Educational / Architecture-Focused)

⚠️ **Disclaimer**\
This project is for educational and architectural demonstration purposes
only.\
It does NOT claim profitability and does NOT provide financial advice.

------------------------------------------------------------------------

## 🎯 Project Goal

The goal of this project is to design a **clear, explainable, and
well-structured trading bot** with a strong focus on engineering
principles rather than financial performance.

This project emphasizes:

- Clean and modular architecture
- Explicit decision-making logic
- Risk management as a first-class concern
- Full observability of decisions and outcomes

### Intentionally Excluded

To avoid hype and over-engineering, the following are **intentionally
not included**:

- Machine Learning
- High-Frequency Trading
- Profit screenshots or claims
- Live or production trading

------------------------------------------------------------------------

## 🧠 High-Level Architecture

The system is intentionally modular and follows a clear pipeline:

    Market Data
       ↓
    Indicator Engine
       ↓
    Strategy Engine
       ↓
    Risk Manager
       ↓
    Execution (Paper / Test)
       ↓
    Logger & Metrics

Each component has a **single responsibility** and can be replaced
independently.

------------------------------------------------------------------------

## 📦 Tech Stack

- **Language:** Python 3.13+
- **Indicators:** pandas, pandas-ta
- **Formatting:** PEP8 (auto-formatted)
- **Execution Mode:** Paper trading / backtesting only

------------------------------------------------------------------------

## 🗂️ Project Structure

    trading_bot/
    ├── data/
    │   └── market_data.py        # Load market data (CSV / mock / future API)
    │
    ├── indicators/
    │   └── indicators.py         # EMA, RSI, trend calculations
    │
    ├── strategy/
    │   └── strategy.py           # Trading decision logic
    │
    ├── risk/
    │   └── risk_manager.py       # Position sizing, stop-loss, limits
    │
    ├── execution/
    │   └── executor.py           # Paper trade execution
    │
    ├── logging/
    │   └── logger.py             # Decisions, trades, metrics
    │
    ├── main.py                   # Orchestrates the full pipeline
    │
    ├── README.md
    ├── CONTRIBUTING.md
    └── requirements.txt

------------------------------------------------------------------------

## 🔍 Strategy Design

Initial strategies implemented in this project include:

- **EMA crossover**
- **RSI with trend filter**

Indicators are sourced from well-known libraries. The value of this
project lies in **how indicators are combined, filtered, and
risk-managed**, not in the indicators themselves.

------------------------------------------------------------------------

## 🛡️ Risk Management Philosophy

Risk management is treated as a **core system**, not an afterthought.

Implemented concepts include:

- Maximum risk per trade (percentage-based)
- Stop-loss rules
- Cooldown periods between trades
- Position sizing logic

A trade can be rejected by the risk manager even if the strategy signals
entry.

------------------------------------------------------------------------

## 📊 Observability & Logging

Every decision made by the system is logged, including:

- Indicator values at decision time
- Strategy decision reasoning
- Risk approval or rejection
- Trade execution outcome

This ensures the system is **auditable, debuggable, and explainable**.

------------------------------------------------------------------------

## 🚀 Running the Project

```bash
pipenv install
pipenv run python main.py
```

------------------------------------------------------------------------

## 🔮 Out of Scope / Future Extensions

The following are intentionally left out but possible in future
iterations:

- Live exchange integration
- WebSocket market feeds
- Multi-asset portfolio support
- Frontend or dashboard visualization

------------------------------------------------------------------------

## 🤝 Contributing

Please read [CONTRIBUTING.md](./CONTRIBUTING.md) before contributing.
