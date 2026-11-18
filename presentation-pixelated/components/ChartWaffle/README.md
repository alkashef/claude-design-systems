Waffle chart of 100 squares that shows how one whole splits, with a legend list and shares beside it.

- Edit `labels` and `values` in `data-chart`, with `"type":"waffle"`. Order the parts largest first and fold small ones into Other.
- Each square is 1%. Shares are rounded to whole squares that total 100, and the legend shows the same numbers.
- Squares fill row by row in legend order, so position carries identity as well as colour. Parts take chart colours 1 to 4 in order. A fifth part takes `chart-muted`: use it for Other. Do not use more than five parts.
- Use it only to show how one whole splits, at a glance. To compare close values, use the bar chart.
- This chart replaces the pie, which cannot be square. In an older deck, `"type":"pie"` draws the same chart.
- Write the source line under the chart.
