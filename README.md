![Retail Data Cleaning & Star Schema](assets/banner_star_schema.png)

# Retail Data Cleaning & Star Schema Modeling — Annual Sales Report

> Cleaning a disorganized retail sales dataset in Excel and modeling it into a professional Power BI star schema, powering an interactive Annual Sales Report dashboard.

## 📌 Overview
This project analyzes annual sales data to uncover performance insights across product categories and sales channels. The raw dataset was cleaned in Excel, then modeled in Power BI as a **star schema** — a central fact table connected to supporting dimension tables — to support fast, reliable reporting.

## 🎯 Objectives
- Clean a messy retail dataset: remove nulls and duplicates, standardize fields.
- Perform **grain analysis** to define the correct level of detail for the fact table.
- Design fact and dimension tables with clear, logical relationships.
- Build calculated columns and DAX measures to power the dashboard.

## 🛠️ Tools & Techniques
- **Excel** — data cleaning: removing nulls and duplicates, standardizing raw data.
- **Power BI** — data modeling, calculated columns, DAX measures, and dashboard visualization.
- **Dimensional Modeling** — star schema design (Kimball approach).

## 🔍 Approach
1. **Data cleaning (Excel)** — removed null values and duplicate records, standardized inconsistent fields in the raw sales data.
2. **Grain analysis** — set the fact table grain at one row per sales transaction line (`AllSales`).
3. **Dimensional design (Power BI)** — split the data into a central fact table and four supporting dimension tables: **Product**, **Channel**, **Region**, and **Calendar**.
4. **Measures layer** — added a dedicated `MeasuresTable` to hold DAX measures (AvgPrice, AVGYOY, MaxDate, MinDate) separate from the data tables, following Power BI best practice.
5. **Relationship building** — connected each dimension to the fact table on its key (ProductID, ChannelID, RegionID, Date), all as clean 1-to-many relationships with no redundant data.
6. **Dashboard build** — used the model to build an interactive Annual Sales Report with KPI cards, category/channel breakdowns, and year-over-year trends.

## 🗺️ Data Model

![Star Schema Data Model](<img width="1246" height="774" alt="image" src="https://github.com/user-attachments/assets/0bbbd26d-a4d3-40e8-8f3b-55dc92a938cc" />
)

**Fact table — `AllSales`**
`ChannelID` · `Date` · `Discount` · `ProductID` · `Quantity` · `RegionID` · `SalesRepID` · `SegmentID`

**Dimension tables**
| Table | Key Fields |
|---|---|
| `Product` | ProductID, Product, Category, Price, CommissionPoints |
| `Channel` | Channel ID, Channel |
| `Region` | Region ID, Region |
| `Calendar` | Date, Month, MonthName, Year |
| `MeasuresTable` | AvgPrice, AVGYOY, MaxDate, MinDate *(DAX measures only)* |

## 🖼️ Dashboard — Annual Sales Report
The model powers an interactive Power BI dashboard with year-over-year KPIs, category and channel breakdowns, and a drill-down table:

![Dashboard Preview](<img width="1434" height="784" alt="image" src="https://github.com/user-attachments/assets/05e1c469-a6bc-4af1-a969-edbe78a83c8c" />
)

## 📊 Key Results (2020)
- **Total Sales:** $10.01M — up **25.6%** year-over-year.
- **Total Quantity:** 1.69M units — up **26.86%** year-over-year.
- **Average Price:** $5.92 (down ~1% YoY).
- **Top category by sales:** Clothing ($0.53M), closely followed by Accessories ($0.51M).
- **Channel mix:** Retail (31.87%) and Key Accounts (30.99%) are the two largest sales channels, with Whole Sale close behind at 31.59%.

## 📁 Repository Structure
```
├── data/                  # raw & cleaned datasets
├── excel/                 # Excel cleaning workbook (nulls & duplicates removed)
├── power_bi/              # .pbix file with the data model & dashboard
├── assets/                # images used in this README
└── README.md
```

## 🚀 How to Run
```bash
git clone https://github.com/AlaaKotbb/retail-data-cleaning-star-schema.git
cd retail-data-cleaning-star-schema
# Review the cleaning steps in excel/
# Open power_bi/model.pbix in Power BI Desktop to explore the model & dashboard
```

## 👤 Author
**Alaa Alkotb** — Data Analyst
[LinkedIn](https://linkedin.com/in/alaa-kotb-5359a42a4) • [GitHub](https://github.com/AlaaKotbb)
