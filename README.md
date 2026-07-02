# Binance Perpetual Funding Rates

USD-M perpetual funding rates from Binance public flat-files.
8-hourly settlements (00:00 / 08:00 / 16:00 UTC), 2020–2026.

## Structure
- `raw/`            — original monthly files, untouched (source of truth)
- `clean/`          — per-symbol consolidated CSVs (sorted, deduplicated)
- `funding_all.csv.gz` — all symbols combined, long format

## Columns
- `calc_time` — settlement timestamp (Unix ms)
- `funding_interval_hours` — settlement interval (usually 8)
- `last_funding_rate` — rate for that 8h period (0.0001 = 0.01%/8h ≈ 11%/yr ×1095)

## Notes
53 symbols incl. delisted/faded (FTT etc.) — survivorship-free.
Source: https://data.binance.vision/data/futures/um/monthly/fundingRate/
