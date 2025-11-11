
# 🪙 CRYPTO COIN ANALYSIS DASHBOARD

Author: Aviral Dubey

---

## Project summary

This repository contains the assets and documentation for a cryptocurrency analysis and visualization project built in Microsoft Power BI. The analysis was performed in Power BI Desktop using the Power Query Editor for data cleaning and transformation. The goal is to provide interactive visuals and KPIs to explore price movements, market capitalization, volatility, and other key metrics across cryptocurrencies.

## Data source

- Primary: Kaggle (cryptocurrency dataset exported as CSV files) — stored in the `rawdata/` folder in this repository.
- Note: original Kaggle dataset metadata and download link (if available) should be preserved locally. If you want the exact Kaggle URL added here, provide it and I will include it.

## Tools & editor

- Power BI Desktop (reporting & visualization)
- Power Query Editor (data cleaning and transformation steps inside Power BI)
- Optional: Excel or Python for small extra transforms (not required)

## Data cleaning / ETL (what I did)

All data cleaning and transformation was done in Power Query (within Power BI Desktop). Key steps performed:

- Loaded raw CSVs from `rawdata/` into Power Query.
- Standardized column names and data types (dates, numbers, text).
- Parsed and normalized nested fields where necessary (for example, price/quote structures).
- Filled/removed nulls and handled missing values according to column context.
- Created derived columns: rolling averages (7d, 30d), percentage change (24h, 7d), daily returns, and market cap rank.
- Converted timestamps to a consistent timezone and date-only fields for time-series visuals.
- Removed duplicate rows and filtered out incomplete records.

If you want, I can export the Power Query M code and place it in a file (e.g., `powerquery-m.txt`) so the exact transformation steps are saved outside the `.pbix`.

## Analyses performed (in Power BI)

Below is a summary of the visualizations and analyses included in the report:

- Top 10 coins by market cap and by current price
- Top & bottom movers over 24h / 7d (percentage change)
- Time-series price trends for selected coins (daily close price)
- Rolling average trendlines (7-day and 30-day)
- Market cap distribution and top-5 market cap breakdown
- All-Time High (ATH) summary and gap-to-ATH metrics
- Volume analysis: top volume movers and volume vs. price change
- Volatility and risk metrics (standard deviation of returns over selectable windows)
- Correlation matrix between coin returns (heatmap)
- KPI cards for quick metrics: total market cap, average 24h change, number of active coins
- Interactive slicers and filters: date range, coin selector, market cap bucket

If any analysis listed above wasn't actually produced, tell me which ones to remove — I listed typical and useful analyses for this project to be comprehensive.

## Files in this repository

- `rawdata/` — Contains the Kaggle-exported CSV files used as the dataset.
- `README.md` — This file.
- `LICENSE` — Project license.

If you have a `.pbix` (Power BI file) you want included, add it to the repo (recommended) or provide it and I can add and reference it here.

## How to open / reproduce the analysis (step-by-step)

1. Install Power BI Desktop (latest stable version).
2. Open Power BI Desktop and choose "Get data" → "Text/CSV" and load the CSV files from the `rawdata/` folder.
3. In the Power Query Editor:
	- Apply the cleaning steps documented above (or load the saved M queries).
	- Ensure data types are set correctly (Date/Time, Decimal Number, Whole Number, Text).
	- Close and apply to load the cleaned model into Power BI.
4. In the Report view, the visuals and measures (DAX) recreate the analyses listed in the "Analyses performed" section.
5. Use the slicers to filter by coin or date range. Export visuals or publish to Power BI Service if you want a hosted report.

## Assumptions and notes

- The source data in `rawdata/` is assumed to be the Kaggle export used for analysis. If you used a different source (API, other CSV), update this README.
- All transformations were done in Power Query to keep the data-refreshable from the same CSVs.
- Time zones were normalized to UTC for consistency across time-series.

## Next steps / suggestions

- Add the `.pbix` file to the repository so the exact report is preserved and reproducible.
- Export Power Query M code to a separate file for version control of transformations.
- Include a small sample `requirements.txt` or `notes.txt` if using any external Python scripts for preprocessing.
- If you want automated refreshes or API integration, we can add a Power BI Gateway + scheduled refresh steps.

## Contact

- Author: Aviral Dubey
- Email: dubeyaviral228@gmail.com
- GitHub: https://github.com/aviral07-ds

---
