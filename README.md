# Regional-Sales-Analysis

## Problem Statement

This project helps sales leadership understand which US regions, sales channels, and products drive the most revenue and profit over a 4-year period, so territory and channel investment decisions can be made with data rather than assumption.

Since the West region ($372.1M) and Wholesale channel ($668.2M) each account for the largest share of the $1.24B total revenue, while profit margins stay flat (~37%) across all regions, the business has an opportunity to look at region-specific pricing rather than a one-size-fits-all margin strategy.

## Steps Followed

- **Step 1**: Loaded `Regional_Sales_Dataset.xlsx` (64,104 orders, Jan 2014 – Feb 2018) into a Python/pandas environment for exploratory data analysis.
- **Step 2**: Used `df.info()` and `df.describe()` to check data types, row counts, and summary statistics across all 21 columns (order details, customer, product, revenue, cost, region, coordinates).
- **Step 3**: Checked for missing values and confirmed the `budget` column had a high null rate; excluded it from profit calculations.
- **Step 4**: Computed order-level **profit** (`revenue - total_cost`) and **profit margin %** for each transaction.
- **Step 5**: Grouped and aggregated data by `us_region`, `channel`, `state_name`, and `order_month` to build region/channel/time trend tables.
- **Step 6**: Exported the cleaned, feature-engineered dataset (`Sales_data_EDA_Exported_.csv`) for use in Power BI.
- **Step 7**: Loaded the exported CSV into Power BI Desktop and built the data model.
- **Step 8**: Created DAX measures for **Total Revenue**, **Total Profit**, **Avg Profit Margin %**, and **Total Units Sold**.
- **Step 9**: Built a geospatial map visual using `lat`/`lon` fields to show state-level revenue concentration across the US.
- **Step 10**: Built a time-series line chart showing monthly revenue and profit trends from 2014 to 2018.
- **Step 11**: Added a channel comparison chart (Wholesale vs Distributor vs Export) and a regional comparison chart (West / South / Midwest / Northeast).
- **Step 12**: Added slicers for Region, Channel, and Year to allow interactive drill-down.
- **Step 13**: Published the report and cross-validated KPI totals against the Python EDA output.

## Key Metrics

| Metric | Value |
|---|---|
| Total Orders | 64,104 |
| Date Range | Jan 2014 – Feb 2018 |
| Customers | 175 |
| Products | 30 |
| States Covered | 47 |
| Regions | 4 |
| Sales Channels | 3 |
| Total Revenue | $1.24B |
| Total Profit | $461.8M |
| Avg Profit Margin | 37.4% |
| Total Units Sold | 541,146 |

## Insights

### [1] Revenue by Region
1. West — $372.1M
2. South — $335.1M
3. Midwest — $320.3M
4. Northeast — $208.4M

### [2] Revenue by Channel
1. Wholesale — $668.2M
2. Distributor — $387.1M
3. Export — $180.6M

### [3] Other Insights
- The West region leads revenue, but the gap to South and Midwest is relatively narrow — the real outlier is Northeast, which trails significantly.
- Wholesale generates more than half of total company revenue, making it the highest-priority channel for retention and growth efforts.
- Profit margin holds steady around 37% regardless of region, suggesting pricing strategy is applied uniformly rather than optimized per region — a potential area to test region-specific pricing.

These figures will change if Region, Channel, or Year filters are applied.
