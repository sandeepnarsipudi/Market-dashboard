
🛒 Market Retail Dashboard (Power BI)

Dashboard Link: https://app.powerbi.com/view?r=eyJrIjoiM2RjNDEwMTYtZGMwYi00OTU2LThmNGItOWNjNDAzNWM2OTNiIiwidCI6IjIzODk2NDkwLTdlNzMtNGQ1Zi1hZjQ5LTBmMjUwMzQ5NWQ3NSJ9

Dashboard Overview

This project presents a **Market Retail Dashboard** built using **Power BI**, with a **CSV file as the data source**. The dashboard provides a consolidated view of retail performance metrics such as sales, profit, revenue, transactions, and customer behavior.

The report contains **a single interactive dashboard page**:

Retail Dashboard

The dashboard is designed to support quick business decision-making by highlighting overall performance and **current month KPIs**.

---

Problem Statement

Retail businesses require continuous monitoring of sales and profitability trends to understand performance at both historical and current levels. This project focuses on delivering a **single-page retail dashboard** with comprehensive KPIs and time-based insights.

Using this dashboard, users can:

* Track overall sales, profit, and revenue
* Monitor transaction trends
* Identify current month performance instantly
* Analyze retail data using multiple KPIs driven by DAX

---

Tools & Technologies Used

* **Power BI Desktop**
* **CSV File (Data Source)**
* **DAX (Data Analysis Expressions)**
* **Retail KPI Design**
* **Single-page Dashboard Architecture**

---

Steps Followed

Data Preparation

* **Step 1:** Retail data was loaded into Power BI using a **CSV file** as the data source.
* **Step 2:** Basic data validation and formatting were performed during data load.
* **Step 3:** Required fields were prepared for KPI and time-based analysis.

Report Design

* **Step 4:** Created a **single Retail Dashboard page** to present all key insights.
* **Step 5:** Designed multiple KPI cards and visuals for sales, profit, revenue, and transactions.
* **Step 6:** Added **three new KPI cards** specifically to track:

  * Current Month Transactions
  
  <img width="260" height="130" alt="Screenshot 2026-02-08 220516" src="https://github.com/user-attachments/assets/a1dfbf43-eca6-4c1f-a3ab-7b7f9cee691c" />

  * Current Month Profit
  
  <img width="259" height="133" alt="Screenshot 2026-02-08 220527" src="https://github.com/user-attachments/assets/46d12417-d918-407c-853f-e29e177847f8" />

  * Current Month Revenue
  
  <img width="264" height="155" alt="Screenshot 2026-02-08 220538" src="https://github.com/user-attachments/assets/adc2c7fe-5347-44c9-bc7c-f9e9f47a170d" />


---

DAX Measures Used

> This project includes **22 DAX measures**.
> Below are representative and commonly used measures, including the **current month KPIs**, written in **Power BI-ready format**.

---

Core Sales Measures

```DAX
Total Revenue =
SUM ( Retail[Revenue] )
```

```DAX
Total Sales =
SUM ( Retail[Sales] )
```

```DAX
Total Profit =
SUM ( Retail[Profit] )
```

```DAX
Total Transactions =
COUNT ( Retail[Transaction_ID] )
```

---

Average & Performance Measures

```DAX
Average Revenue =
AVERAGE ( Retail[Revenue] )
```

```DAX
Average Profit =
AVERAGE ( Retail[Profit] )
```

```DAX
Average Sales =
AVERAGE ( Retail[Sales] )
```

```DAX
Profit Margin % =
DIVIDE ( [Total Profit], [Total Revenue], 0 )
```

---

Time Intelligence – Current Month KPIs ⭐

```DAX
Current Month Revenue =
CALCULATE (
    [Total Revenue],
    MONTH ( Retail[Order_Date] ) = MONTH ( TODAY () ),
    YEAR ( Retail[Order_Date] ) = YEAR ( TODAY () )
)
```

```DAX
Current Month Profit =
CALCULATE (
    [Total Profit],
    MONTH ( Retail[Order_Date] ) = MONTH ( TODAY () ),
    YEAR ( Retail[Order_Date] ) = YEAR ( TODAY () )
)
```

```DAX
Current Month Transactions =
CALCULATE (
    [Total Transactions],
    MONTH ( Retail[Order_Date] ) = MONTH ( TODAY () ),
    YEAR ( Retail[Order_Date] ) = YEAR ( TODAY () )
)
```

---

Additional Analytical Measures

```DAX
Revenue YTD =
TOTALYTD ( [Total Revenue], Retail[Order_Date] )
```

```DAX
Profit YTD =
TOTALYTD ( [Total Profit], Retail[Order_Date] )
```

```DAX
Transactions YTD =
TOTALYTD ( [Total Transactions], Retail[Order_Date] )
```

```DAX
Max Daily Revenue =
MAX ( Retail[Revenue] )
```

```DAX
Min Daily Revenue =
MIN ( Retail[Revenue] )
```

```DAX
Revenue Contribution % =
DIVIDE ( [Total Revenue], CALCULATE ( [Total Revenue], ALL ( Retail ) ), 0 )
```

> Remaining measures follow similar patterns to support dashboard KPIs and comparisons.

---

Key Insights

* Current month KPIs provide real-time visibility into retail performance.
* Profit and revenue trends help identify growth and decline patterns.
* Transaction analysis supports operational and sales planning.
* Single-page dashboard enables fast and effective decision-making.

---

Conclusion

This Market Retail Dashboard demonstrates strong proficiency in **Power BI dashboard design**, **DAX measure creation**, and **retail KPI development**. The project highlights the ability to translate raw CSV data into actionable business insights using a clean and focused single-page dashboard.
