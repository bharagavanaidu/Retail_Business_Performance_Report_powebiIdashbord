# Retail Business Performance & Profitability Dashboard

## Project Overview

This project analyzes retail business performance and profitability
using **Power BI**. The dashboard is designed to provide a
management-level view of revenue, profit, profit margin, category
performance, city performance, seasonal performance, and time-based
trends.

The project focuses on turning retail transaction and profitability data
into interactive business insights that can support performance
monitoring and decision-making.

## Business Objectives

-   Monitor total revenue and total profit.
-   Analyze overall profit margin.
-   Compare profitability across product categories.
-   Identify revenue contribution by city.
-   Understand revenue patterns across categories and seasons.
-   Track revenue and profit trends over time.
-   Allow users to filter the dashboard by city/region and product
    category.
-   Analyze product-level profitability and transaction activity.

## Tools & Technologies

-   **Power BI** -- dashboard development, data modeling and
    visualization
-   **Power Query** -- data preparation and transformation
-   **DAX** -- calculated measures and business metrics
-   **Data Modeling** -- analytical tables and relationships
-   **Data Visualization** -- KPI cards, bar charts, line charts,
    matrix/table visuals and slicers

## Dashboard Contents

The current PBIX contains one dashboard page with 12 visual elements:

1.  **Total Revenue** -- headline revenue KPI.
2.  **Total Profit** -- headline profit KPI.
3.  **Profit Margin %** -- profitability KPI.
4.  **Profit Margin by Category** -- compares category-level margins.
5.  **Revenue by City** -- compares revenue across cities.
6.  **Monthly Revenue & Profit Trend** -- shows revenue and profit over
    time.
7.  **Revenue by Category & Season** -- compares category performance by
    season.
8.  **Product/Category Detail Table** -- product, category, margin and
    transaction information.
9.  **City / Region Slicer** -- interactive geographic filtering.
10. **Product Category Slicer** -- interactive category filtering.
11. **Season KPI** -- displays the selected/current season field.
12. **Dashboard Text Area** -- supporting dashboard content.

## Key Analytical Areas

### Revenue Analysis

Revenue is analyzed at overall, city, category, seasonal and time
levels.

### Profitability Analysis

The dashboard compares total profit and profit margin and provides
category-level profitability analysis.

### Geographic Analysis

The city-level visual helps identify differences in revenue performance
between locations.

### Seasonal Analysis

Category and seasonal revenue are presented together to identify
seasonal differences in product performance.

### Trend Analysis

The time-series visual compares revenue and profit across the reporting
period.

## Dashboard Interactivity

The dashboard includes slicers for:

-   City / Region
-   Product Category

These filters allow users to interactively examine business performance
for specific locations and product categories.

## Data Model

The PBIX contains analytical tables including:

-   `PowerBI_Fact_Sample`
-   `Category_Profitability`
-   `Category_by_Season`
-   `Customer_Category_Profit`
-   `Discount_Impact`
-   `Inventory_Turnover_Proxy`
-   `Monthly_Trend`
-   `Performance_by_City`
-   `Performance_by_StoreType`
-   `Product_Bottom15_Margin`
-   `Product_Top10_Profit`
-   `Promotion_Impact`
-   `Seasonal_Summary`
-   `SlowMoving_Overstock_Risk`

## Dashboard Quality Check

The PBIX structure was reviewed before preparing this repository
documentation.

### Strengths

-   Clear KPI section for revenue, profit and margin.
-   Good mix of KPI, comparison, trend and detail visuals.
-   Category, city and seasonal analysis are covered.
-   Interactive slicers improve exploration.
-   The dashboard is suitable as a portfolio-level Power BI project.

### Recommended Checks Before Final Publication

**1. Validate the Profit Margin % calculation**

The dashboard currently uses a summed `profit_margin_pct` field for the
margin KPI and category visual. For an overall margin KPI, a safer
business definition is:

``` dax
Profit Margin % =
DIVIDE(
    SUM(Category_Profitability[total_profit]),
    SUM(Category_Profitability[total_revenue]),
    0
) * 100
```

Use the equivalent measure based on the actual model grain.

**2. Validate table relationships**

The model diagram currently shows no visible relationship edges. Several
visuals combine fields from `PowerBI_Fact_Sample` with measures/columns
from other analytical tables. Verify that the numbers do not repeat
across cities, dates or categories because of disconnected tables.

**3. Check the monthly trend axis**

The visual is titled `Monthly Revenue & Profit Trend`. Use a proper
Month-Year field sorted by an actual date column so that months appear
chronologically.

**4. Rename the season KPI**

If the card is intended to show a selected season, a clearer title would
be `Selected Season` rather than simply `season`.

## Suggested Repository Structure

``` text
Retail-Business-Performance/
│
├── README.md
├── Retail_Business_Performance_Report.pdf
├── Retail_Business_Performance.pbix
├── dashboard.png
└── DAX/
    └── measures.dax
```

## Skills Demonstrated

-   Power BI Dashboard Development
-   Data Cleaning and Transformation
-   Data Modeling
-   DAX
-   KPI Development
-   Business Analysis
-   Data Visualization
-   Trend Analysis
-   Category Analysis
-   Geographic Analysis
-   Seasonal Analysis

## Portfolio Summary

This project demonstrates how Power BI can be used to transform retail
business data into an interactive performance and profitability
dashboard. The analysis brings together revenue, profit, margin, city,
category, seasonal and time-based views in a single reporting interface.

For portfolio use, the project demonstrates practical skills in **Power
BI, DAX, data modeling, visualization and business-focused analytics**.
