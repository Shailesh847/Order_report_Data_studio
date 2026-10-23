# Order Report Dashboard | Google Data Studio

An interactive retail order dashboard built by connecting an Excel dataset to Google Data Studio (the product was previously called Looker Studio). The project turns thousands of order-line records into an easier way to explore regional demand, product categories, customer segments, cities, and changes over time.

![Order Report Dashboard](orders-report-dashboard.png)

## 1. The story behind the project

I began with a practical business question: **How can a business quickly understand where its orders are coming from, which groups contribute most to order activity, and when demand is rising or falling?**

The Excel file contained nearly 9,994 records. Reading rows one by one would make it difficult to compare regions, categories, segments, and time periods. I connected the worksheet to Data Studio and designed a single interactive report so a viewer could scan the overall picture first, then filter the data to investigate a specific area.

The dashboard brings together KPI cards, filter controls, doughnut charts, a city bar chart, yearly and monthly trend lines, and detail tables. The goal was not only to display numbers, but to make patterns easier to notice and turn them into questions the business could investigate.

## 2. Business problem and questions

A retail team may need to answer questions such as:

- Which regions account for the largest share of order-line activity and quantity?
- Which product categories and customer segments appear most often in the records?
- Which cities have the highest number of order-line records?
- How does quantity change across years and months?
- Does the pattern change when we filter by region, segment, category, or shipping mode?
- Are high-volume categories also the strongest contributors to sales and profit?

The current dashboard helps answer the first five questions. The last question requires adding sales and profit visuals, which are recommended improvements below.

## 3. Dataset overview

| Item | Details |
|---|---|
| Source | `Data Source.xlsx` |
| Records | 9,994 rows / order-line records |
| Fields | 21 columns |
| Order date range | January 3, 2014 – December 30, 2017 |
| Distinct orders | 5,009 unique Order IDs |
| Customers | 793 unique Customer IDs |
| Geography | 49 states and 4 regions |
| Customer segments | Consumer, Corporate, Home Office |
| Product categories | Office Supplies, Furniture, Technology |
| Total quantity | 37,873 units |
| Total sales in source data | $2,297,200.86 |
| Total profit in source data | $286,397.02 |

**Important metric definition:** Each row represents an order line/product record, not necessarily a unique order. One Order ID can appear on multiple rows when an order contains multiple products. Therefore, 9,994 rows and 5,009 distinct orders are different measures.

### Fields used

The dataset includes order dates and IDs, shipping mode, customer IDs and names, segment, city, state, region, product category and sub-category, product name, sales, quantity, discount, and profit.

## 4. Dashboard features

### KPI cards

The report summarizes order records, customers, states, and customer segments. For accuracy, the card currently showing **9,994 as “# of Orders” should be relabeled “Order Lines / Records” or changed to count distinct Order IDs (5,009)**.

### Interactive filters

The left-side controls let viewers narrow the report by:

- **Region:** Compare West, East, Central, and South.
- **Segment:** Focus on Consumer, Corporate, or Home Office.
- **Category:** View Office Supplies, Furniture, or Technology.
- **Ship Mode:** Compare Standard Class, Second Class, First Class, and Same Day.

### Charts and tables

- **Doughnut charts:** Show how order-line records are distributed across regions, categories, and segments.
- **City bar chart:** Compares the number of order-line records in the leading cities.
- **Yearly trend line:** Displays total quantity by order year.
- **Monthly trend line:** Compares total quantity by month across the dataset's four-year period.
- **Order detail table:** Shows order date, order ID, and quantity.
- **State and region table:** Compares quantity across states and regions.
- **Customer table:** Ranks customer IDs by quantity.

The report combines a high-level view with detail tables so users can move from a broad pattern to the records behind it.

## 5. Key insights from the dashboard

### 1. The West leads in both record activity and quantity

In the current region doughnut, the West accounts for **32.1% of records** (3,203 rows), followed by East at 28.5%, Central at 23.2%, and South at 16.2%.

When I sum the Quantity field separately, the West also leads with **12,266 units (32.4%)**, followed by East with 10,618 (28.0%), Central with 8,780 (23.2%), and South with 6,209 (16.4%).

The percentages differ slightly because one chart counts records while the other sums units. Quantity alone does not explain profitability.

### 2. Office Supplies is the largest category by records and quantity

The current category doughnut shows Office Supplies as **60.3% of records** (6,026 rows), with Furniture at 21.2% and Technology at 18.5%.

Summing the Quantity field gives a similar pattern: Office Supplies accounts for **22,906 units (60.5%)**, Furniture 8,028 (21.2%), and Technology 6,939 (18.3%).

This indicates Office Supplies is the largest category by activity and unit volume, but a business should still compare sales and profit before assuming it is the most valuable category financially.

### 3. Consumer records make up the largest segment share

Consumer represents **5,191 order-line records (51.9%)**. Corporate contributes 3,020 (30.2%) and Home Office contributes 1,783 (17.8%).

This makes the Consumer segment a useful place to start when exploring product mix or customer behavior. These percentages describe records in the dataset, not the percentage of unique customers.

### 4. New York City leads the city record count

New York City has **915 order-line records**, ahead of Los Angeles (747), Philadelphia (537), San Francisco (510), and Seattle (428).

These counts point to cities with more recorded line-item activity; they should not be described as unique-order counts unless the chart is changed to count distinct Order IDs.

### 5. Quantity increased over the years shown

The yearly trend rises from **7,581 units in 2014** to **12,476 in 2017**, an increase of about **64.6%** between those years.

This suggests that recorded unit volume grew over the period. To understand whether the growth also improved business performance, it should be compared with sales, profit, discount levels, and changes in the number of orders.

### 6. November is the strongest month by total quantity

When quantity is aggregated across all four years, **November has 5,775 units**, followed by December with 5,419 and September with 5,062. January and February have the lowest totals.

This may help the business investigate seasonal demand and plan stock or campaigns, but the pattern should be checked year by year before making a seasonal plan.

### 7. California has the highest state quantity

California records **7,667 units**, followed by New York with 4,224 and Texas with 3,724.

The state-and-region table makes it easier to see where recorded volume is concentrated and select locations for deeper analysis.

### 8. Standard Class is the most common shipping mode

Standard Class appears on **5,968 records (about 59.7%)** and accounts for 22,797 units.

This suggests that most recorded line items use the standard shipping option. Delivery speed, shipping cost, customer satisfaction, and late delivery rates would need to be added before deciding whether this shipping mix is optimal.

## 6. Further business findings from the same Excel data

The current dashboard focuses on record counts and quantity trends. I also checked the Sales, Profit, and Discount fields in the source data to identify useful next questions. These findings are **additional analysis from the worksheet**, not all visuals currently displayed in the dashboard.

### Sales and profit tell a different story from quantity

- **Technology** leads in sales at about **$836,154** and profit at about **$145,455**, with a profit margin of roughly **17.4%**.
- **Office Supplies** leads in quantity but produces about **$719,047** in sales and **$122,491** in profit.
- **Furniture** produces about **$742,000** in sales but only about **$18,451** in profit, a margin of roughly **2.5%**.

This is an important distinction: the highest-volume category is not automatically the strongest by sales or profit. Furniture deserves a closer review of discounting, cost, and sub-category performance.

### High discounts deserve a closer look

There are **1,393 records with discounts of 30% or more**. Together, those records represent about **$362,770 in sales and -$135,376 in profit**.

This does not prove that discounts alone caused the losses, but it is a strong reason to investigate discounted products, sub-categories, and pricing rules.

### Geographic volume does not always mean strong profit

The Central region has the lowest regional profit margin in the source data at about **7.9%**. Philadelphia records about **$109,077 in sales but -$13,838 in profit**.

These examples show why a more decision-oriented dashboard should display sales and profit alongside quantity and order activity.

## 7. How Google Data Studio works

Google Data Studio (known as Looker Studio for a period) is a reporting and visualization tool. It connects to a data source, lets the analyst select fields, and turns those fields into charts, tables, scorecards, and filter controls. Google documents a Microsoft Excel connector for using a worksheet as a data source.

### Key concepts I learned

- **Data source / connector:** Links the report to an underlying file or system. The connector determines what fields are available and how data is accessed.
- **Dimensions:** Descriptive fields used to group data, such as Region, Segment, Category, City, State, Ship Mode, and Order Date.
- **Metrics:** Values that can be measured or aggregated, such as Quantity, Sales, Profit, record count, and distinct-order count.
- **Aggregation:** Specifies how a metric is calculated. `SUM(Quantity)` adds units, a record count counts rows, and `COUNT_DISTINCT(Order ID)` counts unique order IDs. Selecting the wrong aggregation can make a chart look correct while answering the wrong question.
- **Scorecards / KPI cards:** Summarize a key metric at the top of a report.
- **Filter controls:** Let a viewer interact with the report without editing the underlying charts.
- **Calculated fields:** Create new measures from existing fields, for example profit margin = total profit divided by total sales.
- **Charts and tables:** Present comparisons and trends in different ways. Bar charts help compare categories; line charts help show time-based changes; tables help inspect detailed values.

### My workflow

1. **Understand the data:** Review the columns and decide which business questions the fields can answer.
2. **Connect the Excel worksheet:** Choose the Microsoft Excel data source connector and check that the correct worksheet is selected.
3. **Check field types:** Verify that order dates are recognized as dates, category fields as dimensions, and quantity, sales, and profit as numeric metrics.
4. **Choose the right aggregation:** Use row counts when measuring line-item records, `SUM(Quantity)` for units, and distinct counts for unique orders or customers.
5. **Build the report layout:** Place KPI cards first, then region/category/segment comparisons, time trends, and supporting tables.
6. **Add controls:** Use region, segment, category, and ship-mode filters to let viewers investigate subsets of the data.
7. **Validate the results:** Compare the numbers shown in charts with the source data and make sure each chart title describes the metric it actually measures.
8. **Turn observations into business questions:** Identify where to investigate further rather than treating a chart as proof of a cause.

## 8. What I learned

- How to connect an Excel worksheet to a reporting tool.
- How to distinguish dimensions from metrics.
- How aggregation choices affect KPI cards and charts.
- How to use filter controls to make a dashboard interactive.
- How to combine scorecards, doughnut charts, bar charts, trend lines, and tables in one report.
- How to move from a visual observation to a business question.
- Why metric definitions and validation are as important as dashboard design.

## 9. Improvements I would make next

1. **Fix the order KPI:** Change the 9,994 label to “Order Lines” or use a distinct count for the 5,009 actual orders.
2. **Make chart labels precise:** The region/category/segment doughnuts and city bars count records, while the state table and time trends show summed quantity. Label them clearly or standardize the aggregation.
3. **Add sales and profit cards:** Total sales, total profit, and profit margin would show whether higher volume is financially healthy.
4. **Add a profit-by-category and profit-by-region view:** Highlight categories or locations with high sales but weak profit.
5. **Add discount analysis:** Compare discount bands with profit and drill down to sub-category and product.
6. **Add year-over-year comparisons:** Include sales, quantity, and profit growth instead of quantity alone.
7. **Improve the time analysis:** Add a date-range control and compare the same month across different years before making seasonal decisions.
8. **Polish usability:** Keep number formats consistent, make titles explicit about units/aggregation, check text readability, and test that all filters affect the intended charts.

## 10. Project summary

This project started as an exploration of an Excel order dataset and became an interactive report for understanding geographic demand, category mix, customer segments, and order activity over time.

The biggest lesson was that a dashboard is not just a collection of charts: each visual needs a clear business question, a correctly defined metric, and a label that tells the truth about what is being counted.

The next version will focus on moving from activity reporting to performance reporting by including sales, profit, discount impact, and more precise order metrics.
