# Bike Sales – Excel Data Cleaning & Dashboard

An Excel project where I take a raw dataset of 1,000+ customers, clean it, analyse it with pivot tables and build an interactive dashboard to see **what kind of customer is most likely to buy a bike**.

![Dashboard](dashboard.png)

---

## Dataset

Customer data with: marital status, gender, income, children, education, occupation, home owner, cars, commute distance, region, age, and whether they **purchased a bike** (Yes/No).

## Tools

- Microsoft Excel (data cleaning, nested `IF` formulas, pivot tables, pivot charts, slicers)

---

## Workbook structure

| Sheet | What's in it |
|-------|--------------|
| `bike_buyers` | The raw data, kept untouched in case I need to go back to it |
| `Working Sheet` | The cleaned copy I did all the work on |
| `Pivot Table` | The pivot tables behind the charts |
| `Dashboard` | The final dashboard with charts and slicers |

## Data cleaning

- **Kept the raw data separate** and did all the cleaning on a copy.
- **Removed 26 duplicate rows** (1,026 rows down to 1,000).
- **Made the values readable:** `M` / `S` → `Married` / `Single`, and `M` / `F` → `Male` / `Female`.
- **Formatted income** as currency.
- **Renamed `10+ Miles` to `More than 10 Miles`** so it sorts at the end of the commute distances in the pivot tables and charts instead of in the wrong place.
- **Added an `Age Brackets` column** with a nested `IF` formula, so age can be analysed in groups instead of 60+ separate ages:
  ```
  =IF(L2>54,"Old",IF(L2>=31,"Middle Age",IF(L2<31,"Adolescent","Invalid")))
  ```

## Analysis & dashboard

Three pivot tables, each with a chart on the dashboard:

1. **Average income** by gender, split by whether they bought a bike
2. **Commute distance**, number of buyers vs non-buyers
3. **Age bracket**, number of buyers vs non-buyers

Three **slicers** (Marital Status, Education, Region) are connected to all three pivot tables, so the whole dashboard filters at once.

## Findings

- Overall, **48% of customers bought a bike** (481 out of 1,000).
- **Buyers earn slightly more:** their average income was about $58k vs $55k for non-buyers, and this is true for both men and women.
- **Shorter commutes buy more:** over half of people commuting up to 1 mile bought a bike (55%), but only 30% of people commuting more than 10 miles did. The 2–5 mile group was actually the highest at 59%.
- **Middle-aged customers (31–54) are the best target:** 55% of them bought a bike, compared to 35% of the youngest group and 31% of the over-55s.

## What I learned

- Always keep a copy of the raw data before cleaning.
- Short codes like `M` / `S` are fine for storing data, but full words make the pivot tables and dashboard much easier to read.
- How labels are written affects how they sort (`10+ Miles` vs `More than 10 Miles`).
- Connecting slicers to every pivot table makes one interactive dashboard instead of separate charts.

## Credit

This project follows the Excel portfolio project from [Alex The Analyst's](https://www.youtube.com/@AlexTheAnalyst) Data Analyst Bootcamp.
