# Exercise 05 — Major Swings Detector

An indicator tool that finds the 3 major rises and 3 major declines of a chart over the last N years, with full details for each move.

The tool:

* Looks back `N` years (configurable `2`–`10`, default `3`) and shades the analysed period on the chart.
* Splits price action into swing legs with a zigzag-like tracker: a leg flips direction only after a `T%` countermove (configurable `5`–`50`, default `10`).
* Stores every leg (direction, start/end bar, start/end time, start/end price) in a custom `Leg` type.
* Picks the 3 biggest rises and 3 biggest declines by percent change, with a non-containment rule: a major rise must not contain any of the 3 major declines inside it, and a major decline must not contain any of the 3 major rises.
* Marks confirmed swing tops/bottoms with `we had ↑` / `we had ↓` labels.
* Shows a results table (top-right) with rank, percent change (+points), start → end dates, start → end prices, and duration in days — green rows for rises, red rows for declines.
