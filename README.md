# 2024-2025-Australian-taxes

Prepared capital gain/loss entries for Hnry (FIFO) based on:
- `Account info for U14217549_20240701_20250630.htm` (Interactive Brokers trades / closed lots)
- `Reserve bank of Australia f11.1-data.csv` (RBA daily AUD/USD rates)

## Output files

- `hnry_capital_gain_loss_from_share_sales_2024_2025.csv`
  - Hnry-ready rows with:
    - `date_of_purchase`
    - `purchase_price_aud`
    - `date_of_sale`
    - `sale_price_aud`
  - Includes `symbol`, `quantity`, and `capital_gain_loss_aud` for checking.
- `capital_gains_hnry_fifo_2024_2025.csv`
  - Full working file with USD values and FX-rate details used for conversion.

## Notes and assumptions used

- Yes — for Hnry’s “capital gain/loss from sale of shares”, you should enter purchase date, purchase price, sale date, and sale price for each disposal line.
- FIFO was taken from IBKR’s `Closed Lot` entries in the Trades section.
- Purchase and sale values are converted to AUD using RBA `A$1=USD` rates.
- Where a trade date had no RBA daily row (e.g. weekend), the latest prior available business-day rate was used.
- A single broker sell can map to multiple FIFO closed lots; those are split into separate rows so each row has one purchase date.

## Quick check

- Number of Hnry rows: 28
- Total capital gain/loss (AUD): 4318.03
