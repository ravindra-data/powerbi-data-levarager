# ⚡ Data Leverager — Power BI Power Query Project

A comprehensive Power BI project demonstrating end-to-end data ingestion, transformation and modelling using Power Query — combining 3 years of sales data with customer demographics, GDP and regional data into a clean, analysis-ready data model.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| Tool | Microsoft Power BI Desktop |
| File | Data_Leverager.pbix |
| Total Tables | 6 (4 source + 2 transformation output) |
| Data Sources | Sales 2020-22, Customers, Country GDP, Region Territory |
| Key Operations | Append Queries, Merge Queries, Data Cleaning |

---

## 🗂️ Data Sources

| Source | Format | Description |
|---|---|---|
| Sales Data 2020-22 | CSV/Excel | Raw transactional sales records across 3 years |
| Customers Data | CSV/Excel | Customer demographics and profile information |
| Country Wise GDP | CSV/Excel | GDP figures by country for economic context |
| Region Territory | CSV/Excel | Mapping of regions to geographies |

---

## 🔄 Power Query Transformations

### 1. Append Queries → `Append Sales Data`
- 3 separate annual sales files (2020, 2021, 2022) stacked vertically
- Column names aligned before appending to avoid schema mismatch
- Result: Single unified sales table covering full 2020–2022 period

### 2. Merge Queries → `Merge Data`
- Customers Data merged with Append Sales Data using Customer ID key
- Left Outer Join — retained all sales records with matching customer attributes
- Result: Fully enriched table combining transactional + demographic data

### 3. Data Quality & Cleaning Steps

| Step | What Was Done |
|---|---|
| Promote Headers | First rows promoted as column headers |
| Rename Columns | Standardized to business-friendly names |
| Change Data Types | Dates → Date type, Revenue → Decimal Number |
| Remove Errors | Error rows filtered at step level |
| Replace Nulls | Nulls → 0 (numeric) or 'Unknown' (text) |
| Remove Duplicates | Duplicates removed on Order ID column |
| Filter Rows | Invalid rows excluded from final output |

---

## 🗃️ Data Model — 6 Tables

| Table | Type | Role |
|---|---|---|
| Sales Data 2020-22 | Source | Annual sales input to Append |
| Customers Data | Dimension | Customer profiles input to Merge |
| Country Wise GDP | Dimension | Economic reference data |
| Region Territory | Dimension | Geographic mapping |
| Append Sales Data | Transformation | Combined 3-year sales fact table |
| Merge Data | Transformation | Enriched sales + customer analytic table |

---

## 🛠️ Tech Stack

- **Tool:** Microsoft Power BI Desktop
- **Feature:** Power Query Editor
- **Operations:** Append Queries, Merge Queries (Left Outer Join), Data Type Conversion, Null Handling, Duplicate Removal

---

## 📁 Project Structure

```
powerbi-data-leverager/
│
├── Data_Leverager.pbix                    # Main Power BI file
├── PowerBI_DataLeverager_Summary.pdf      # Transformation summary report
├── screenshots/
│   └── report.png                         # Report preview
└── README.md                              # Project documentation
```

---

## 🚧 Challenges & Solutions

| Challenge | Solution |
|---|---|
| Appending 3 yearly sales files | Used Append Queries — aligned column names first |
| Joining sales with customer data | Applied Merge Queries with Customer ID key |
| Inconsistent column headers | Promoted headers + renamed columns uniformly |
| Dates stored as text | Applied Change Type → Date conversion |
| Null and error values | Used Remove Errors + Replace Values steps |
| Duplicate sales records | Applied Remove Duplicates on Order ID |

---

## 💡 What I Learned

- Loading and shaping multiple data sources in Power Query Editor
- Using Append Queries to combine 3 years of sales data vertically
- Applying Merge Queries (Left Outer Join) to enrich sales with customer data
- Performing full data cleaning — nulls, errors, duplicates, type conversion
- Building a clean 6-table data model ready for DAX and visualization

---
