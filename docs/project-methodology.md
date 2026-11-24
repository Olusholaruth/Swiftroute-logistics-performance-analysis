# Project Methodology

## 1. Business context

SwiftRoute Logistics is a case-study logistics company seeking clearer visibility into revenue, profitability, shipment activity, delivery outcomes, and operational delays.

The analysis is designed to turn shipment-level records into management-focused summaries and an interactive dashboard.

## 2. Data preparation

The source project brief identifies deliberate data-quality issues, including duplicate records, inconsistent categorical formatting, and unsuitable data types. The preparation workflow should:

1. Inspect the source fields and understand their business meaning.
2. Identify duplicate records and apply an appropriate removal rule.
3. Standardize inconsistent category values.
4. validate date and numeric data types.
5. Check the prepared record count and confirm the data is suitable for analysis.

Do not assume that every repeated Shipment_ID is automatically a duplicate without checking the intended record grain.

## 3. Excel analysis

The requested analysis covers:

- Revenue by destination region
- Revenue, profit, and shipment count by package category
- Carrier shipment count, revenue, profit, and delay days
- Monthly revenue, profit, and shipment volume
- Revenue generated from Lagos deliveries
- Profit from the South West region
- Average delay for Express shipments
- Lagos shipment volume
- Revenue by customer type
- Financial and volume comparison by service type
- Delay days by destination region
- Evidence-based management observations

PivotTables are appropriate for grouped comparisons; conditional calculations should be used for filtered business questions where appropriate.

## 4. Power BI KPI definitions

The following definitions describe the intended business meaning. The implemented DAX should be checked against the actual model and field values.

| KPI | Business definition |
|---|---|
| Total Revenue | Sum of shipment revenue |
| Total Profit | Sum of shipment profit |
| Total Shipments | Distinct count of valid Shipment_ID values |
| Total Delay Days | Sum of recorded delay days |
| Late Shipment Rate | Late shipments divided by distinct valid shipments, expressed as a percentage |
| Lagos Revenue | Revenue filtered to destination city Lagos |
| Lagos Delayed Shipments | Distinct late shipments filtered to destination city Lagos |
| South West Delay Days | Delay days filtered to the South West destination region |

For the late shipment rate, the numerator and denominator must use the same shipment grain. Confirm that the Delivery_Status values and Delay_Days logic agree before interpreting the result.

## 5. Dashboard analysis

The dashboard scope includes revenue and profit trends, regional revenue, package-category profitability, carrier revenue and delivery performance, delivery-status distribution, regional delays, service-type performance, leading destination cities, revenue-versus-profit comparison, customer segment shipment volume, and distance/delivery performance.

Useful slicers include destination region, carrier, service type, package category, and customer type.

## 6. Validation and communication

Before publishing findings:

- Reconcile headline totals with the prepared dataset and Excel outputs.
- Check distinct shipment counts and filter context.
- Confirm that percentage measures use the intended denominator.
- Verify that filtered KPIs respond correctly to slicers.
- State the time period and relevant population for each finding.
- Separate observed results from recommendations.

No numerical business insight should be published until it has been checked against the completed workbook or report.
