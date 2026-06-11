# Bibitor LLC CFO Dashboard

## Project Overview
Power BI dashboard for Bibitor LLC, a retail wine and spirits company with 60 locations and $450-500M in annual sales.

## Business Requirements
The dashboard addresses the following CFO requests:

1. **Store-level performance** - Sales per square foot, gross margin %, sales, gross profit, units sold
2. **Top 5 product categories** by sales
3. **Product performance** with emphasis on products below 10% gross margin
4. **Key Performance Indicators** - Sales, gross profit, gross margin %, units sold
5. **Sales by product class** for the top 5 counties

## Data Sources
| File | Description |
|------|-------------|
| WeeklyStoreSales.csv | Sales transactions by store, brand, week |
| StandardPurchasePrices.csv | Product master with purchase prices |
| BrandClassification.csv | Brand to class/category mapping |
| ClassCategories.csv | Class category descriptions (Spirit, Wine) |
| StoreLocations.csv | Store details with square footage |
| CountyDemographics.csv | County-level demographic data |

## Key Measures Created
- Total Sales = SUMX(FactSales, Units × AverageSalesPrice)
- Total Cost = SUMX(FactSales, Units × RELATED(PurchasePrice))
- Gross Profit = [Total Sales] - [Total Cost]
- Gross Margin % = DIVIDE([Gross Profit], [Total Sales], 0)
- Sales per Sq Ft = DIVIDE([Total Sales], SUM(SquareFootage), 0)

## Data Limitations (2022 Only)
- No prior year data for year-over-year comparison
- Seasonal patterns based on single year may not be reliable
- Store manager bonuses cannot be calculated without prior year and expense data

## Files Included
- `Bibitor_CFO_Dashboard.pbix` - Main Power BI file
- `dashboard_screenshot.png` - Dashboard visual
- `data_model_screenshot.png` - Star schema data model

## How to Use
1. Open the .pbix file in Power BI Desktop
2. Use the slicers to filter by date, store, or county
3. Click on any store to cross-filter all visuals
4. Sort Product Performance Table by Gross Margin % to identify problem products


