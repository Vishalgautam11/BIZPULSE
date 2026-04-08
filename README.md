

# BizPulse — End-to-End Business Analytics Pipeline

> From raw data to boardroom insights — Python | SQL | Power BI

---

## Project Overview

BizPulse is a full-stack business analytics project that simulates a real-world SaaS/e-commerce analytics pipeline. Starting from synthetic data generation in Python, through SQL-based metric engineering, to an interactive Power BI dashboard — this project demonstrates the complete workflow a Business Analyst or Data Analyst performs in a professional environment.

---

## Tech Stack

| Layer | Tool |
|---|---|
| Data Generation | Python (Pandas, NumPy, Faker) |
| Data Storage & Transformation | SQL Server (T-SQL) |
| Reporting & Visualization | Microsoft Power BI |

---

## Project Architecture

```
Python (Data Generation)
        ↓
   CSV Export
        ↓
SQL Server (Metric Engineering)
        ↓
   Power BI (Dashboard)
```

---

## Dataset

Synthetically generated user activity dataset with the following fields:

- `user_id`, `username`, `email` — User identity
- `signup_date`, `activity_date` — Temporal activity
- `status` — Active / Inactive / New / Lost
- `product_id` — Product interaction
- `spend` — User-level spend
- `rps` — Revenue per session

**Rows:** ~2,000 user records across 12 months (Jan–Dec 2024)

---

## SQL Metrics Engineered

### Table 1 — Monthly Overview
| Metric | Description |
|---|---|
| Monthly User Spend | Total spend by users per month |
| Monthly Company Spend | Simulated acquisition spend per month |
| Profit / Loss | User Spend minus Company Spend |
| MOM Growth Rate | Month-over-month % change in P&L using LAG() |
| Total New Users | Count of new signups per month |
| CAC | Customer Acquisition Cost = Company Spend / New Users |

### Table 2 — Churn Analysis
| Metric | Description |
|---|---|
| Total New Users | New signups per month |
| Total Lost Users | Inactive users per month |
| Churn Rate % | Lost Users / New Users × 100 |

---

## Power BI Dashboard

### Page 1 — Executive Summary
- KPI Cards: Total User Spend, Total Company Spend, Total P&L, Total New Users
- Monthly User Spend vs Company Spend (Clustered Bar)
- Profit/Loss by Month (Table with conditional formatting)
- Average CAC by Month (Bar Chart)

<img width="1318" height="728" alt="Page -1" src="https://github.com/user-attachments/assets/d927fc4b-7911-43ef-ad94-8db067a40fb1" />




### Page 2 — Monthly Performance
- Monthly User Spend vs Company Spend (Clustered Bar)
- Profit/Loss by Month (Waterfall Chart)
- MOM Growth Rate Trend (Line Chart)

<img width="1304" height="730" alt="PAGE - 2" src="https://github.com/user-attachments/assets/c4b10184-0724-4b96-84b8-7e3d708b3060" />



### Page 3 — CAC & Acquisition
- Monthly User Spend vs CAC (Combo Chart — Bar + Line)
- New Users per Month (Bar Chart)
- Monthly User Status Trend — Active, Inactive, Lost, New (Multi-line Chart)



<img width="1310" height="733" alt="Page - 3" src="https://github.com/user-attachments/assets/0a46c5ed-054a-4fb1-9021-6a512ea98d32" />



---

## Key Business Insights

- Company operated at a **net loss of ~₹58K** across the year
- Only **4 months were profitable** — March, April, August, September
- **Highest CAC** was in March (₹1,082) — coinciding with highest company spend
- **December** saw the highest new user acquisition (201 users) but worst P&L (-₹57K)
- **Churn rate** averaged ~57% monthly — indicating retention as a key business challenge

---

## How to Run

### Step 1 — Generate Dataset
```bash
pip install pandas numpy faker
python data_generation.py
```
This creates `REPORT_1.CSV`

### Step 2 — Load into SQL Server
- Import `REPORT_1.CSV` into SQL Server as `REPORT_1` table
- Run `sql_metrics.sql` to create `MONTHLY_OVERVIEW` and `CHURN_TABLE`

### Step 3 — Power BI
- Open `BizPulse_Report.pbix` in Power BI Desktop
- Connect to your SQL Server instance
- Refresh data

---

## Folder Structure

```
BizPulse/
├── data_generation.py       # Python script to generate synthetic dataset
├── REPORT_1.CSV             # Generated dataset
├── sql_metrics.sql          # All SQL queries for metric engineering
├── BizPulse_Report.pbix     # Power BI dashboard file
└── README.md
```

---

## Skills Demonstrated

- Synthetic data generation using Python
- SQL window functions — `LAG()`, `PARTITION BY`, `GROUP BY`
- Business metric engineering — CAC, MOM Growth Rate, Churn Rate, P&L
- Data modeling and table relationships in Power BI
- Dashboard design and storytelling with data

---

## Author

**Vishal**
B.Tech CSE (AI & Data Science) — IIIT Senapati, Manipur
Targeting: Business Analyst | Data Analyst | Operations Analyst

