# Exercise 04 — Fibonacci SR Strategy

A 1-minute timeframe strategy trading Pin Bar and Engulfing reactions at Fibonacci support/resistance levels derived from the previous day's range.

The strategy:

* Uses the previous day's high and low (`1440` × 1-minute bars) to define the daily range.
* Plots Fibonacci retracement levels at `0.234`, `0.38`, `0.5`, `0.618`, and `0.78` as support/resistance zones.
* Detects bullish and bearish Pin Bars (long shadow `> 2 × body`, opposite shadow `< body`).
* Detects bullish and bearish Engulfing candles forming right after the previous candle.
* Opens Long or Short positions when a Pin Bar or Engulfing touches/breaks any Fibonacci level.
* Enters only when flat (`strategy.position_size == 0`) — no new position until the open one is closed.
* Sets Stop Loss and Take Profit to the nearest Fibonacci levels (or previous high/low at the edges).
* Displays the previous high/low and all five Fibonacci levels on the chart.
