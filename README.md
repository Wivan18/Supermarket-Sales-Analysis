# Supermarket Sales Analysis Dashboard (Power BI)

A three-page Power BI report analyzing supermarket produce sales — covering sales value, quantity sold, and a combined quantity-vs-sales comparison — across items, categories, discounts, and time. The report spans **1 July 2020 to 30 June 2023**.

---

## 📊 Report Pages

### 1. Sales of Products
The primary revenue-focused page, tracking sales value (#Amount) across time and product dimensions.

**Key Metrics (KPI Cards)**
| Metric | Value |
|---|---|
| #Amount (total) | 3.37M |
| #Quantity (total) | 470.98K |
| Amount for 2023 | 563.10K |
| Amount for 2022 | 1.04M |

**Visuals**
- **#Amount by Year** — area/line chart 2020–2023, rising from 0.67M (2020) to a peak of 1.10M in 2021, holding at 1.04M in 2022, then dropping to 0.56M in 2023 (partial year).
- **#Amount by Item Name** — ranked horizontal bar chart led by Broccoli (0.27M), followed by Net Lotus Root (0.21M), Xixia Mushroom (0.21M), Wuhu Green Pepper (0.21M), Yunnan Shengcai (0.13M), down to Spinach (0.05M).
- **#Amount by Discount (Yes/No)** — donut chart showing the overwhelming majority of sales value (3.21M, 95.22%) comes from non-discounted sales, with only 0.16M (4.78%) from discounted transactions.
- **#Amount by Category Name** — donut chart led by Flower/Leafy vegetables (1.08M, 32.02%), Capsicum (0.75M, 22.38%), Edible Mushrooms (0.62M, 18.4%), Cabbage (0.35M, 10.39%), and smaller shares from Aquatic and Solanum categories.

**Slicers**: Date (range slider), Item Name, Discount (Yes/No), Sale or Return, Category Name.

---

### 2. Quantity of Products
Mirrors the Sales page structure, but shifts the lens from revenue to unit volume (#Quantity).

**Key Metrics (KPI Cards)**
| Metric | Value |
|---|---|
| #Amount (total) | 3.37M |
| #Quantity (total) | 470.98K |
| Qty for 2023 | 85.66K |
| Qty for 2022 | 161.30K |

**Visuals**
- **#Quantity by Year** — area/line chart 2020–2023, rising from 86.58K (2020) to 137.43K (2021), peaking at 161.30K in 2022, then falling sharply to 85.66K in 2023.
- **#Quantity by Item Name** — ranked bar chart led by Wuhu Green Pepper and Broccoli (28K each), Net Lotus Root (27K), Chinese Cabbage (21K), Yunnan Shengcai (16K), down to Zhuyecai (7K).
- **#Quantity by Discount (Yes/No)** — donut chart: 439.22K units (93.26%) sold without discount vs. 31.75K units (6.74%) sold with discount.
- **#Quantity by Category Name** — donut chart led by Flower/Leafy vegetables (198.5K, 42.1%), Capsicum (91.59K, 19.45%), Edible Mushrooms (76K, ~16%), Cabbage (40K, ~8%), Aquatic (41K, ~8%).

**Slicers**: Date (range slider), Item Name, Discount (Yes/No), Sale or Return, Category Name.

**Notable pattern**: Quantity peaks in **2022**, one year later than the Amount peak in **2021** — suggesting either falling average unit prices in 2022, or a promotional push that boosted volume without proportionally boosting revenue.

---

### 3. Quantity vs Sales
A combined comparative page pairing volume and value metrics directly against each other.

**Key Metrics** — identical KPI cards to the prior two pages (#Amount 3.37M, #Quantity 470.98K, Qty for 2023 85.66K, Qty for 2022 161.30K), used here for consistent cross-page reference.

**Visuals**
- **#Quantity and #Amount by Year** — dual-line/area combo chart overlaying both metrics 2020–2023. Amount (red) consistently outpaces Quantity (green) in scale, both following the same rise-peak-decline shape, with Amount peaking at 1.24M in 2021 and Quantity peaking around similar visual scale in 2022 — confirming the one-year lag between the two peaks noted above.
- **#Quantity and Average of Unit Selling Price by Item Name** — combo column/line chart comparing per-item quantity sold against average unit selling price, item-by-item across the full product catalog.
- **#Quantity and #Amount by Item Name** — dual-bar horizontal chart, ranking items by both quantity and amount side-by-side (e.g., Wuhu Green Pepper: 28.16K units / 205.11K amount; Broccoli: 27.54K units / 269.88K amount — showing Broccoli generates more revenue despite slightly lower volume, implying a higher unit price).

**Slicers**: Date (range slider), Item Name, Discount (Yes/No), Sale or Return, Category Name.

---

## 🧭 Navigation
The three pages share an identical filter panel layout (Date, Item Name, Discount, Sale or Return, Category Name) and KPI card positioning, making them designed for side-by-side tab comparison rather than a drill-through hierarchy.

## 🔍 Filters Used Across Pages
- **Date** — range slicer spanning July 2020 to June 2023.
- **Item Name** — filter down to a single produce item (e.g., Broccoli, Chinese Cabbage, Yunnan Shengcai).
- **Discount (Yes/No)** — isolate discounted vs. full-price transactions.
- **Sale or Return** — filter between sales transactions and returns.
- **Category Name** — filter by produce category (Flower/Leafy Vegetables, Capsicum, Edible Mushrooms, Cabbage, Aquatic, Solanum).

## 📌 Key Insights
1. **2021 was the revenue peak, 2022 the volume peak** — #Amount peaked in 2021 (1.10M) while #Quantity peaked a year later in 2022 (161.30K), indicating declining average selling prices or a volume-driven discount strategy in 2022.
2. **2023 shows a sharp decline** in both metrics (Amount: 0.56M, Quantity: 85.66K), roughly half of the prior year on a partial-year basis — worth checking if this reflects a shortened reporting period or an actual downturn.
3. **Discounted sales are a small share of the business** — under 7% of both quantity and revenue comes from discounted transactions, suggesting discounting isn't a major volume driver for this store.
4. **Flower/Leafy Vegetables is the leading category** in both revenue (32%) and quantity (42%), but its revenue share is notably lower than its volume share — implying this category carries a lower average price point than others like Capsicum or Edible Mushrooms.
5. **Broccoli and Wuhu Green Pepper are volume leaders**, but per-unit revenue comparisons (e.g., Broccoli: 269.88K revenue on 27.54K units vs. Wuhu Green Pepper: 205.11K revenue on 28.16K units) show Broccoli commands a meaningfully higher price per unit despite near-identical volume.
6. **Top ~20 items account for the visible ranking** in every "by Item Name" visual, with a long tail of lower-volume items likely present but scrolled below the visible range.

## 🛠️ Tech Stack
- **Power BI Desktop** — report authoring, DAX measures, Power Query (M) for data transformation.
- **Data model** — date table supporting year-level aggregation across all three pages.
- **Visuals** — KPI cards, donut/pie charts, area/line trend charts, horizontal ranked bar charts, and dual-metric combo charts, styled in a consistent green (sales/quantity) and red (comparison) palette.

## 📁 Suggested Repo Structure
```
Supermarket-Sales-Analysis-PowerBI/
├── README.md
├── SupermarketSalesAnalysis.pbix
├── screenshots/
│   ├── 01-sales-of-products.png
│   ├── 02-quantity-of-products.png
│   └── 03-quantity-vs-sales.png
└── data/
    └── (source data or data dictionary, if shareable)
```

## ✍️ Author
Built by **Wawire Ivan Wekesa (Ivan Wawire)** — Data Analyst & BI Developer.
