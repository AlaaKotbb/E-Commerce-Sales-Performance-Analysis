![Retail Data Cleaning & Star Schema](<img width="1280" height="320" alt="banner_star_schema" src="https://github.com/user-attachments/assets/5a745ff2-98b8-4c38-b8be-60e246b82f39" />
)

# Retail Data Cleaning & Star Schema Modeling

> Cleaning a disorganized, error-prone retail dataset and restructuring it into a professional star schema for scalable analytics and reporting.

## 📌 Overview
This project takes a messy, real-world-style retail sales dataset and transforms it into a clean, well-modeled **star schema** in Power BI — a central fact table connected to supporting dimension tables — ready for reliable reporting.

## 🎯 Objectives
- Clean and standardize a disorganized retail dataset.
- Perform **grain analysis** to define the correct level of detail for the fact table.
- Design fact and dimension tables with clear, logical relationships.
- Remove redundancy and improve query performance for reporting.

## 🛠️ Tools & Techniques
- **SQL** — data cleaning and transformation.
- **Power BI** — data modeling and relationship management.
- **Dimensional Modeling** — star schema design (Kimball approach).

## 🔍 Approach
1. **Data profiling** — explored the raw dataset to identify quality issues (duplicates, inconsistent formats, missing keys).
2. **Grain analysis** — set the fact table grain at one row per sales transaction line (`AllSales`).
3. **Dimensional design** — split the data into a central fact table and four supporting dimension tables: **Product**, **Channel**, **Region**, and **Calendar**.
4. **Measures layer** — added a dedicated `MeasuresTable` to hold DAX measures (AvgPrice, AVGYOY, MaxDate, MinDate) separate from the data tables, following Power BI best practice.
5. **Relationship building** — connected each dimension to the fact table on its key (ProductID, ChannelID, RegionID, Date), all as clean 1-to-many relationships with no redundant data.

## 🗺️ Data Model
v<img width="1246" height="774" alt="image" src="https://github.com/user-attachments/assets/eea752c8-cbdc-4d0d-9316-52e0f0c68460" />


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

## 📊 Result
A clean, scalable star schema that supports fast, reliable reporting — with a single source of truth for products, channels, regions, and dates, and no duplicated or redundant data.

## 🖼️ Dashboard Preview
The model powers an interactive Power BI **Annual Sales Report**, with year-over-year KPIs, category and channel breakdowns, and a drill-down table:

![Dashboard Preview](v<img width="1434" height="784" alt="image" src="https://github.com/user-attachments/assets/2f0a0024-e3a6-4271-83a4-7f90d263f014" />
)

## 📁 Repository Structure
```
├── data/                  # raw & cleaned datasets
├── sql/                   # cleaning & schema-creation scripts
├── power_bi/              # .pbix file with the data model
├── assets/                # images used in this README
└── README.md
```

## 🚀 How to Run
```bash
git clone https://github.com/AlaaKotbb/retail-data-cleaning-star-schema.git
cd retail-data-cleaning-star-schema
# Run the SQL scripts in /sql to rebuild the schema
# Open power_bi/model.pbix in Power BI Desktop to explore the model
```

## 👤 Author
**Alaa Alkotb** — Data Analyst
[LinkedIn](https://linkedin.com/in/alaa-kotb-5359a42a4) • [GitHub](https://github.com/AlaaKotbb)
