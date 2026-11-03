# Synthetic data notes

Every row in both CSVs is synthetic and was authored for this demo. These are invented illustrative amounts, not measurements, forecasts, or results from an actual business. There are no customer records or personal identifiers.

## Monthly revenue

[monthly-revenue.csv](monthly-revenue.csv) has one row per month, January through June 2026.

| Field | Type | Meaning |
| --- | --- | --- |
| `month` | ISO year-month string | Calendar month; preserve chronological order |
| `revenue_usd` | Integer | Synthetic total monthly revenue in USD |
| `is_synthetic` | Boolean text (`true`) | Every row is synthetic |

| Month | Revenue (USD) |
| --- | ---: |
| 2026-01 | 120,000 |
| 2026-02 | 135,000 |
| 2026-03 | 128,000 |
| 2026-04 | 150,000 |
| 2026-05 | 165,000 |
| 2026-06 | 180,000 |

June minus January is $60,000, a 50% increase relative to January. March is $7,000 lower than February. The six-month sum is $878,000. There are no missing months or duplicate keys.

## Category comparison

[category-comparison.csv](category-comparison.csv) breaks the June 2026 synthetic total into mutually exclusive demo product categories.

| Field | Type | Meaning |
| --- | --- | --- |
| `month` | ISO year-month string | All rows are June 2026 |
| `category` | String | Invented product category name |
| `revenue_usd` | Integer | Synthetic category revenue in USD |
| `is_synthetic` | Boolean text (`true`) | Every row is synthetic |

| Category | Revenue (USD) |
| --- | ---: |
| Platform | 80,000 |
| Analytics | 60,000 |
| Support | 40,000 |

The sum is $180,000, matching June in the monthly CSV. This fixture is a breakdown, not an additional $180,000 to add to the monthly series. There are no duplicate month/category keys.

## File conventions

Files are UTF-8 CSV with headers, comma delimiters, and unformatted integer amounts. Boolean values need explicit conversion if your CSV reader returns strings. Displaying `$80k` means $80,000 USD; it does not change the stored value.

The [briefs](../briefs/monthly-revenue.json) describe chart decisions, and the [static examples](../examples/monthly-revenue.svg) illustrate them. Update all related artifacts together when changing a fixture. Keep the synthetic label visible wherever figures are reused.
