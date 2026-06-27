# Executive Sales Dashboard using Tableau

## Business Problem Summary

The retail leadership team requires an executive dashboard to monitor overall business performance across sales, profitability, customer segments, product categories, shipping efficiency, discount strategy, and product returns.

The objective of this dashboard is to help executives identify high-performing areas, detect operational risks, and support data-driven business decisions.

---

# Dataset Description

The dataset contains retail transaction data with approximately 4,200 records.

### Available Fields

- Order ID
- Order Date
- Ship Date
- Customer ID
- Customer Segment
- Region
- State
- City
- Category
- Sub-Category
- Product Name
- Ship Mode
- Sales
- Quantity
- Discount
- Profit
- Return Flag
- Delivery Days
- Customer Rating
- Campaign Channel

The dataset contains:

- Date fields
- Geographic fields
- Categorical variables
- Numerical measures
- Binary return indicator

---

# Tableau Workbook Description

The workbook contains an executive dashboard designed for leadership reporting.

The dashboard includes:

- Sales Trend
- Regional Performance
- Category Profitability
- Customer Segment Analysis
- Shipping Performance
- Discount vs Profit Analysis
- Return Analysis

---

# Calculated Fields

### Profit Margin

```
SUM([Profit]) / SUM([Sales])
```

### Cost

```
SUM([Sales]) - SUM([Profit])
```

### Average Order Value

```
SUM([Sales]) / COUNTD([Order ID])
```

### Return Rate

```
SUM(IIF([Return Flag]="Yes",1,0))
/
COUNT([Order ID])
```

### Shipping Delay Bucket

```
IF [Delivery Days] <=2 THEN "Fast"
ELSEIF [Delivery Days] <=5 THEN "Standard"
ELSE "Delayed"
END
```

---

# Dashboard Components

The executive dashboard includes:

- KPI Cards
  - Total Sales
  - Total Profit
  - Profit Margin
- Sales Trend Line Chart
- Regional Performance Chart
- Category Profitability Chart
- Customer Segment Chart
- Shipping Performance Chart
- Discount vs Profit Scatter Plot
- Return Analysis

---

# Filters Used

Interactive filters include:

- Region
- Category
- Customer Segment
- Order Date
- Ship Mode
- Campaign Channel

Dashboard action filters allow chart selections to filter the remaining views.

---

# Key Business Insights

- Sales fluctuate throughout the reporting period.
- Certain regions consistently outperform others.
- Some product categories generate high revenue but low profitability.
- Heavy discounting reduces profitability.
- Delayed shipping is associated with lower customer satisfaction.
- Customer segments differ in profitability.
- Product returns are concentrated in selected categories.
- Executive attention should focus on pricing strategy and logistics efficiency.

---

# Dashboard Story Summary

The dashboard connects sales performance, profitability, customer behavior, shipping efficiency, and returns into a single executive view.

Leadership can quickly identify opportunities for growth while monitoring operational risks.

---

# Assumptions

- Return Flag contains "Yes" and "No".
- Profit Margin is calculated from aggregated Sales and Profit.
- Average Order Value is calculated using distinct orders.
- Delivery Days represents shipping duration.
- Missing values are assumed to be minimal.

---

# Limitations

- Dashboard uses historical transactional data only.
- External factors such as seasonality and market conditions are not included.
- Customer lifetime value is unavailable.
- Inventory information is unavailable.

---

# Screenshots Included

- full_dashboard.png
- sales_trend_view.png
- regional_performance_view.png
- category_profitability_view.png
- filter_interaction_view.png
