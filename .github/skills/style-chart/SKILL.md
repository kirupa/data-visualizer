---
name: style-chart
description: Create chart styling and accessibility specifications from a chart brief. Use when asked to style a chart, choose chart colors, improve axis labels, prepare slide visuals, or make chart guidance more accessible.
---

# Style a chart

Write a concrete styling specification for an existing brief. Styling must preserve the underlying values, scale decisions, and meaning.

## Read the resources

- [Design tokens](../../../assets/design/chart-tokens.json)
- [Monthly chart brief](../../../assets/briefs/monthly-revenue.json)
- [Category chart brief](../../../assets/briefs/category-comparison.json)
- [Static monthly illustration](../../../assets/examples/monthly-revenue.svg)
- [Static category illustration](../../../assets/examples/category-comparison.svg)
- [Source data notes](../../../assets/data/README.md)

The SVGs are static worked examples. Do not claim they demonstrate responsive behavior, hover tooltips, or keyboard interaction.

## Workflow

1. Read the supplied brief and confirm its chart type, field mappings, units, synthetic status, audience, and medium. If the brief is missing, request it or label your assumptions. Don't quietly change the chart type to fit a design.
2. Use the light-background tokens as the default. Record exact foreground/background pairs. Calculate contrast for proposed colors: target at least 4.5:1 for ordinary text and 3:1 for large text and essential graphical marks against adjacent backgrounds. Treat these as checks, not a certification of accessibility.
3. Specify canvas dimensions, plot margins, font sizes, tick spacing, line width, marker shape, and bar spacing. For a slide, start with the 960 by 540 worked-example canvas and check readability at the actual presentation size. For another size, re-evaluate layout; do not merely scale tiny text.
4. Keep the baseline and units visible. Use a zero baseline for magnitude bars. Preserve chronological ordering for time series. Use `$120k` for a 120000 USD axis/point label only when the chart explicitly defines USD thousands.
5. Use one series color unless the brief requires multiple series. Convey series identity with direct labels plus distinct markers or line patterns as well as color. Do not use red/green alone for positive/negative values.
6. Write a factual title, synthetic-data subtitle, axis labels, summary, and table alternative. Label observed changes without invented causes. If smoothing is requested, explain that a smooth curve could imply unobserved intermediate values.
7. For SVG output, require a `viewBox`, `role="img"`, a linked `title` and `desc`, and readable visible labels. For an interactive implementation outside this demo, separately specify keyboard navigation, focus visibility, accessible control names, and a non-hover route to data.
8. Check clipping, overcrowding, contrast, and readability in the actual output when available. If only source or a brief is available, mark visual and assistive-technology checks as unverified.

## Expected output

Return a styling specification with exact token values, dimensions, axis/label rules, non-color cues, text alternative, table source, and a short list of checks still needed. State any necessary deviation from the tokens and explain why.

Do not output CSS, a renderer, or image files unless requested. Do not claim a static source inspection proves screen-reader or slide-projector usability.

## Worked check

The bundled monthly chart uses a solid blue line with circular markers on white. The category chart uses blue bars with category names and numeric labels. Both have a zero-to-200000 USD scale, displayed as USD thousands, and visible synthetic disclosures. These are single-series examples; the multi-series palette has not been demonstrated by these figures.

## Data handling

Keep all sample data explicitly synthetic. Preserve numeric values and currency when shortening labels. Do not embed confidential source rows or personal identifiers in SVG metadata, accessible descriptions, screenshots, or demo slides.
