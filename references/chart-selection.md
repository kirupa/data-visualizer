# Chart selection reference

Start with the reader's question and the structure of the available data. The same dataset may support several questions, each with a different useful chart.

| Question | Starting choice | Required fields | Watch for |
| --- | --- | --- | --- |
| How does a measure change over time? | Line with observed-point markers | Ordered time and numeric measure | Gaps, irregular intervals, smoothing, and too many series |
| Which category is larger? | Horizontal bars | Category and numeric magnitude | Nonzero baselines, long labels, and unclear ordering |
| How are two measures related? | Scatterplot | Paired numeric observations | Overplotting, outliers, and causal claims |
| How are values distributed? | Histogram | Individual numeric observations | Bin-width choices and hidden tails |
| How do parts contribute to a whole? | Stacked bars; simple pie only for a few nonnegative parts | Parts with one defined common total | Missing parts, changing denominators, and negative values |
| What is the exact value? | Table | Labels and values with units | Rounding that conceals meaningful differences |

## Scale and ordering rules

Magnitude bars start at zero because their lengths encode values. A line chart can use a narrower domain when small variation is the question, but disclose that choice and retain context. The monthly worked example starts at zero to keep the demo comparison straightforward.

Use chronological order for time. Use magnitude order for a ranking question unless a meaningful domain order is more useful. Keep ordinal categories such as small, medium, and large in their natural order.

Do not replace nulls with zero or silently drop incomplete periods. Specify aggregation before combining duplicate rows. Rates require denominators; an average of rates is not necessarily the overall rate.

## Bundled examples

[Monthly revenue](../assets/data/monthly-revenue.csv) is a single synthetic series covering January through June 2026. Its [brief](../assets/briefs/monthly-revenue.json) recommends a line for change over time. Connecting observed months does not establish daily values or causes.

[Category revenue](../assets/data/category-comparison.csv) compares synthetic June 2026 amounts. Its [brief](../assets/briefs/category-comparison.json) recommends horizontal bars for ranking. The categories total $180,000, equal to June's monthly value.

## Before sharing

Check title, units, baseline, dates, categories, source, synthetic disclosure, and accessible summary. Provide a table alongside the visual when exact lookup matters. Color needs supporting labels or shapes; no palette alone proves accessibility.
