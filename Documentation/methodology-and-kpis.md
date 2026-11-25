# Methodology and KPI Definitions

## Data preparation

The capstone brief identifies duplicates, inconsistent categorical formatting and unsuitable data types as intentional quality issues. It asks for duplicate removal with record-count verification, category standardisation, appropriate data types, valid date fields, usable numeric fields and validation before analysis.

The supplied Excel workbook contains 100,000 raw records and 98,000 cleaned records (excluding headers), across 20 columns.

## Excel calculations documented in the workbook

| Measure | Result |
|---|---:|
| Lagos revenue | ₦230,405,681.69 |
| Lagos shipment count | 19,637 |
| South West profit | ₦172,319,276.64 |
| Express average delay | 0.8865 days |

The workbook's service comparison reports:

| Service | Average revenue | Average profit | Average shipping cost | Shipments |
|---|---:|---:|---:|---:|
| Standard | ₦9,820.08 | ₦4,206.01 | ₦5,614.07 | 58,853 |
| Express | ₦13,304.84 | ₦5,695.01 | ₦7,609.82 | 27,335 |
| Same Day | ₦17,162.61 | ₦7,359.29 | ₦9,803.32 | 11,812 |

## Power BI KPI definitions required by the brief

| KPI | Definition from the brief |
|---|---|
| Total Revenue | Overall revenue generated across the dataset |
| Total Profit | Overall profit generated across the dataset |
| Total Shipments | Number of unique valid shipments after data preparation |
| Total Delay Days | Total recorded delay days |
| Late Shipment Rate | Percentage of shipments classified as Late |
| Lagos Revenue | Revenue from shipments delivered to Lagos |
| Lagos Delayed Shipments | Number of Late shipments delivered to Lagos |
| South West Delay Days | Total delay days for shipments delivered within the South West region |

The brief requires at least three filtered KPIs to use `CALCULATE()` appropriately to demonstrate filter context.

## Important metric distinction

The brief defines **Lagos Delayed Shipments** using the `Delivery_Status = "Late"` classification. A measure based only on `Delay_Days > 0` answers a different question: it counts shipments with positive recorded delay days, regardless of delivery-status classification. These definitions should not be treated as interchangeable.

Likewise, the brief defines **Late Shipment Rate** by the Late status classification. A rate based on positive delay days is a different metric.

## Interpretation cautions

- Compare total delay days with shipment volume; a high total may reflect a high number of shipments.
- Distinguish totals from averages when comparing service types or carriers.
- Describe associations and patterns; do not claim causation from descriptive analysis alone.
- Validate every KPI against the cleaned data and the business definition before presenting it as final.