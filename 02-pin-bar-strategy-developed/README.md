# Exercise 02 — Pin Bar Strategy (Developed)

An improved version of the Pin Bar strategy with a candlestick body-based volatility measure, engulfing confirmation, and pluggable trade-state modes.

The strategy:

* Detects bullish and bearish Pin Bars across three body/shadow profiles (small, medium, and large bodies relative to volatility).
* Confirms signals with a bullish or bearish Engulfing candle appearing after the Pin Bar.
* Calculates volatility as `80%` of the average candle body over `100` bars.
* Detects bullish and bearish trends when price moves more than `2 × ATR` away from the EMA.
* Opens Long or Short positions when a valid Pin Bar + Engulfing sequence appears within `1 × ATR` of the EMA.
* Uses a `3 × ATR` Stop Loss.
* Supports Risk/Reward ratios of `1`, `2`, or `3`.
* Switches between three trade-state modes (enter only when flat, close and reverse on every signal, or reverse only on opposite signals) through a custom library.
* Displays the EMA range, Stop Loss, and Take Profit levels on the chart.

