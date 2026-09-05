# Exercise 03 — Pin Bar Strategy (Optimised)

A refactored and optimised version of the Pin Bar strategy, rebuilt with user-defined types and cleaner logic.

The strategy:

* Stores candle features (body, shadows, and their ratios to volatility) in a custom `candle` type.
* Stores market features (`ATR`, `EMA`, bounds, and trend flags) in a custom `marketInfo` type.
* Detects bullish and bearish Pin Bars across three body/shadow profiles (small, medium, and large bodies relative to volatility).
* Calculates volatility as `80%` of the average candle body over `100` bars.
* Detects bullish and bearish trends when price moves more than `2 × ATR` away from the EMA, and invalidates them when price crosses back over the EMA.
* Detects Pin Bars only when price is within `1 × ATR` of the EMA, with no Engulfing confirmation required.
* Uses a `3 × ATR` Stop Loss.
* Supports Risk/Reward ratios from `1` to `3`.
* Switches between three trade-state modes (enter only when flat, close and reverse on every new signal, or reverse only on opposite signals).
* Displays the EMA range, Entry, Stop Loss, and Take Profit levels on the chart.

