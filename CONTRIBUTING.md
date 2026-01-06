# Contributing Guide

Thank you for contributing 🙌\
This project values **clarity, architecture, and explainability** over
features or performance.

------------------------------------------------------------------------

## 🧠 Core Principles

All contributions should follow these principles:

1. Architecture \> Features
2. Explainability \> Performance
3. Risk awareness \> Profit claims
4. Readability \> Clever code

------------------------------------------------------------------------

## 🧱 Code Style Guidelines

- Follow **PEP8**
- Use auto-formatting tools before committing
- Prefer explicit, descriptive naming
- **Comments and docstrings are allowed only for:**
  - Business logic explanation
  - Utility/helper functions
- Exception: functions or classes with >3 inputs or high internal complexity

### Examples

✅ Good

``` python
calculate_position_size()
```

❌ Bad

``` python
calc_ps()
```

------------------------------------------------------------------------

## 🧩 Module Responsibility Rules

Each module must have **one clear responsibility**.

- Indicators → calculate values only
- Strategy → decide, not execute
- Risk → approve or reject trades
- Execution → simulate trades only
- Logging → record decisions and metrics

Avoid cross-module side effects.

------------------------------------------------------------------------

## 🤖 Copilot-Friendly Development

This project is designed to be built with AI assistance (e.g., Copilot).

Please ensure: - Clear function docstrings - Type hints for public
functions - Deterministic and predictable behavior

### Example

``` python
def should_enter_trade(
    ema_fast: float,
    ema_slow: float,
) -> bool:
    """
    Decide whether to enter a trade
    based on EMA crossover logic.
    """
    ...
```

------------------------------------------------------------------------

## 🚫 What NOT to Add

- Guaranteed profit claims
- Hard-coded API keys or credentials
- Obfuscated or overly clever logic
- Unnecessary abstractions

------------------------------------------------------------------------

## 📝 Commit Message Guidelines

Use clear and descriptive commit messages:

✅ `add risk-based position sizing`\
❌ `update stuff`

------------------------------------------------------------------------

## 🧪 Testing Philosophy

Formal automated tests are optional at this stage.

However: - Functions should be deterministic - Outputs should be
predictable - Logs should explain *why* a decision was made

------------------------------------------------------------------------

## 📣 Final Review Checklist

Before submitting a change, ask:

> "Would a technical reviewer understand this in under 2 minutes?"

If not, simplify the implementation.
