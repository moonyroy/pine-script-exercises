# Exercise 08 — Top 10 Daily Candles

An indicator that finds the 10 biggest daily candles of any symbol and shows them ranked by size in a table.

The tool:

* Measures each candle's size as `(high - low) / open`.
* Keeps a rolling top-10 list: fills it with the first `10` bars, then replaces the smallest entry whenever a bigger candle appears.
* Stores each top candle's size and `time` in parallel arrays.
* Shows a top-right table with `Rank`, `Date` (`yyyy-MM-dd HH:mm` in the chart timezone), and `Range` (`0.000%` format), sorted biggest-first via `array.max(rank - 1)`.
* Colors rows with a gradient from orange (`#ffba3b`) to green by rank.
