# Exercise 07 — Directional Fibonacci Strategy

A 1-minute style strategy trading Pin Bar and Engulfing reactions at directional Fibonacci levels built from the previous day's range.

The strategy:

* Tracks the previous day's high, low, open, close and range (`mvm`) bar by bar, rolling them over on `timeframe.change("D")`.
* Detects the last daily leg direction (`leg_up`): whichever extreme (high or low) printed last decides the leg, with the daily close breaking ties.
* Builds directional Fibonacci levels at `0.23`, `0.34`, `0.50`, `0.61`, and `0.78`, measured down from the daily high when the leg is up, or up from the daily low when the leg is down.
* Filters volatility with the average candle body over `1440` bars: Pin Bars need a body `> avg / 2` with a long shadow `> 1.5 × body`, Engulfings need a body `> 1.5 × avg` closing beyond the prior candle's extreme.
* Enters Long only when price holds above a level (`max(low[1], low[2])` and `close` above it) with a Pin Bar wicking below it or an Engulfing dipping below it (mirrored logic for Shorts).
* Trades only small candles (`high - low < mvm / 6`) and only when flat — one position at a time via a `lng` / `sht` state.
* Sets Take Profit to the nearest Fibonacci level in the trade direction (falling back to the daily high/low) and Stop Loss to the second-nearest level behind the entry.
* Plots entry, stop, profit, daily high/low, and all five Fibonacci levels on the chart.
