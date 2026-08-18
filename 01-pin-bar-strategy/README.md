# Exercise 01 — Pin Bar Strategy

Create a Pine Script strategy based on Pin Bar patterns, EMA, and volatility.

The strategy:

* Detects bullish and bearish Pin Bars based on candle body and shadow proportions.
* Uses a configurable `EMA` with a default length of `21`.
* Calculates volatility using the average candle body over `100` bars.
* Detects bullish and bearish trends when price moves more than `2 × ATR` away from the EMA.
* Opens Long or Short positions when a valid Pin Bar appears within `1 × ATR` of the EMA.
* Uses a `3 × ATR` Stop Loss.
* Supports Risk/Reward ratios of `1`, `2`, or `3`.
* Displays the EMA range, Stop Loss, and Take Profit levels on the chart.
