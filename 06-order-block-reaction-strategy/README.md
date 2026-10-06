# Exercise 06 — Order Block Reaction Strategy

A strategy that enters on Pin Bar reactions to Order Blocks formed at the end of a trend, with FVG confirmation.

The strategy:

* Detects an uptrend when `3` consecutive closes print above the prior candle's high with rising lows (mirrored logic for a downtrend).
* Tracks the trend extreme (`trackHigh` / `trackLow`) and invalidates the trend if price breaks back beyond its origin (`trendLow` / `trendHigh`).
* Marks a bearish Order Block as the high-to-low of the candle ending an uptrend when its upper shadow is the trend top, the next candle is red, and its body is large enough to leave an FVG gap between the OB low and the high two candles later (mirrored logic for a bullish OB).
* Invalidates the Order Block if price breaks beyond its far edge (`high > obTop` for shorts, `low < obBot` for longs).
* Enters Short on a bearish Pin Bar reaction: body `> 0`, upper shadow `>= 2 × body`, lower shadow `<= body`, high inside the OB (`obBot <= high <= obTop`), close below the OB (`close < obBot`), and the upper shadow never breaking the OB top.
* Enters Long on the mirrored bullish Pin Bar reaction at a bullish Order Block.
* Uses the far OB edge as Stop Loss (`obTop` for shorts, `obBot` for longs) with a configurable Risk/Reward of `1`, `2`, or `3`.
* Runs a state machine (`""` → trend → order block → in trade) so only one position is managed at a time.
