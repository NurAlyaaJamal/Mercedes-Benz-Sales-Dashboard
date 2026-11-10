# Mercedes-Benz Car Sales Dashboard (2020–2025)

An interactive two-page Power BI dashboard built on more than 12 million units of Mercedes-Benz sales (global, 2020–2025). The Overview page shows the headline numbers and the main breakdowns. The Analysis page looks at price, power and revenue by model and year.

![Overview](screenshots/overview.png)

![Analysis](screenshots/analysis.png)

## Key numbers

| Measure | Value |
|---|---|
| Total revenue | $1.26T |
| Total units sold | 12.13M |
| Average price | $104.22K |
| Average horsepower | 367 hp |
| Units with a turbo | 85.48% |

## What the dashboard shows

- **GLC is the top model:** 2.09M units and about $238.9B in revenue, roughly 19% of all revenue. GLE and GLS follow in revenue.
- **2023 was the peak year** for revenue ($242.9B). The latest year is lower than the one before it, with revenue down about 5.6% and units down about 9.8% on 2024.
- **Petrol is the largest fuel type** at about 48% of units, followed by Diesel (21%), Hybrid (20%) and Electric (11%). Electric has the highest average price (about $109K).
- **Black and white cars** account for nearly half of all units.
- **The 80K+ price band** sells far more units than any other band.

## Pages

**Overview**
- Five KPI cards, with year-on-year change for revenue and units
- Units and revenue by year, top 10 models, fuel type share
- Units by colour, units by price band, average price by fuel type
- Slicers for year, fuel type, turbo and model, plus a Clear all slicers button

**Analysis**
- Price vs horsepower by model (bubble size = units sold)
- Top 10 models by revenue, split by year
- Revenue heatmap: model × year
- Key insights panel

## How it was built

1. **Data cleaning and preparation in Power Query:** a `Revenue` column (base price × sales volume) and a `Price Band` column (Under 40K, 40K–60K, 60K–80K, 80K+).
2. **DAX measures:** Total Units, Total Revenue, Average Price, Average Horsepower, Turbo %, and year-on-year change measures for the revenue and units cards.
3. **Report design:** a dark theme with a silver, black and teal palette, custom fuel-type and car colours, top-N filters, and a page navigator.

**Tools:** Power BI Desktop, DAX, Power Query. The report is saved as a Power BI Project (PBIP), so the report and model are plain text files that work well with Git.

## Repository contents

```
├── README.md
├── screenshots/                 Dashboard screenshots
├── dashboard.pdf                Both pages exported as PDF (optional)
├── powerbi-project/
│   ├── Mercedes-Benz Car Sales Dashboard.pbip
│   ├── Mercedes-Benz Car Sales Dashboard.Report/          Pages and visuals
│   └── Mercedes-Benz Car Sales Dashboard.SemanticModel/   Tables, measures, DAX
└── data/
    └── sample_1000_rows.csv     Small sample (the full file is too large for GitHub)
```

## How to open it

1. Install Power BI Desktop (Windows) and enable **File → Options → Preview features → Power BI Project (.pbip) save option**.
2. Open `powerbi-project/Mercedes-Benz Car Sales Dashboard.pbip`.
3. The report expects the full CSV (`mercedes_benz_sales_2020_2025.csv`). It is not included because of its size. Place your copy anywhere, then point to it in **Home → Transform data → Data source settings → Change Source**.

## Data

| Column | Description |
|---|---|
| Model | Car model (A-Class, C-Class, GLC, and others) |
| Year | 2020–2025 |
| Region | Global only |
| Color | Car colour |
| Fuel Type | Petrol, Diesel, Hybrid, Electric |
| Base Price (USD) | Price per car |
| Horsepower | Engine power |
| Sales Volume | Units sold in the row |
| Turbo | Yes / No |

[ADD DATA SOURCE HERE, for example the Kaggle dataset link]

**Notes on the data:** the values are spread very evenly across years and models, so differences between groups are small. For example, average horsepower is almost the same with or without a turbo. The dashboard is designed to make those comparisons easy to read.

## Author

**Nur Alyaa Jamal**, Data Analyst
[LinkedIn](https://www.linkedin.com/in/nur-alyaa-jamal13/) · [GitHub](https://github.com/NurAlyaaJamal)
