# NexaLink Telecom — Customer Churn Analysis

An end-to-end data analytics project investigating customer attrition patterns, revenue impact, and retention strategy for a fictional telecommunications company.

---

![Dashboard Overview](assets/screenshots/01_overview.png)
*<!-- Hero image — Replace with your best overview page screenshot (full width). Upload to assets/screenshots/01_overview.png -->*

---

## Project Overview

NexaLink is a telecommunications provider offering internet, phone, and streaming services to residential customers. The company faces a critical churn problem: **26.5% of its customer base (1,869 of 7,043 customers) has churned**, representing an estimated **$1.67 million in annualised revenue loss** — equivalent to **30.5% of total monthly revenue**.

This project investigates the root drivers of churn across seven analytical dimensions, quantifies the financial impact of each segment, and delivers a prioritised retention strategy with ROI projections. The analysis follows a structured framework: **Observation → Insight → Impact → Recommendation**.

**Role:** Data Analyst — responsible for data preparation, exploratory analysis, semantic model design, DAX measure creation, and report development in Power BI.

---

## Tools Used

- **Power BI** — Dashboard design, DAX measures, data modelling (TMDL/PBIP format)
- **Microsoft Excel** — Data source, schema design, data cleaning
- **GitHub** — Version control and portfolio publishing

---

## Data Model

Star schema with one fact table and four dimension tables, all joined on `Customer_ID` with bidirectional cross-filtering:

| Table | Type | Key Columns |
|-------|------|-------------|
| `fact_churn` | Fact | Customer_ID, Monthly_Charge_USD, Churned, Tenure_Months, Ticket counts |
| `dim_customer` | Dimension | Customer_ID, Gender, Senior_Citizen, Has_Partner, Has_Dependents |
| `dim_billing` | Dimension | Customer_ID, Contract_Type, Payment_Method, Paperless_Billing |
| `dim_services` | Dimension | Customer_ID, Internet_Service_Type, Add-on subscriptions |
| `dim_support` | Dimension | Customer_ID, Admin_Tickets_Count, Tech_Tickets_Count |

![Data Model](assets/screenshots/07_data_model.png)
*<!-- Data model diagram — Add a screenshot of the Power BI model view showing the star schema. Upload to assets/screenshots/07_data_model.png -->*

---

## Key Findings

- **Month-to-month contracts drive 88.6% of churn** — customers on flexible terms churn at 42.7%, 15× the rate of two-year contract customers (2.8%)
- **A single tech support ticket triples churn probability** — from 19.7% (0 tickets) to 65.6% (1+ tickets), the sharpest churn inflection point in the dataset
- **Fiber optic customers churn at 41.9%** and account for 69.4% of all churned customers, despite being only 44% of the base
- **Electronic check users churn at 45.3%** — 2.7–3.0× the rate of automatic payment customers — representing ~60% of total churn volume
- **Protective add-ons cut churn by more than half** — customers without online security churn at 41.8% vs. 14.6% for those with it (2.86× multiplier)
- **Compound risk peaks at 78.9% churn** — customers with both high charges (>$70.35) and 2+ tech tickets are nearly 5× more likely to leave than the baseline

---

## Dashboard Pages

| Page | Content |
|------|---------|
| Overview | Executive KPIs, top-5 churn drivers ranked by severity, revenue impact summary |
| Demographics | Churn by gender, senior status, partner/dependents — segment size and churn rate |
| Tenure & Loyalty | Churn by tenure band, early-tenure vulnerability, customer lifecycle analysis |
| Services & Add-ons | Internet type impact, protective add-on retention effect, streaming services null finding |
| Contract & Billing | Contract type analysis, payment method risk, paperless billing proxy variable |
| Charges & Revenue | Monthly charge thresholds, revenue loss breakdown, financial impact summary |

### Overview

![Overview Page](assets/screenshots/01_overview.png)
*<!-- Upload to assets/screenshots/01_overview.png -->*

### Demographics

![Demographics Page](assets/screenshots/02_demographics.png)
*<!-- Upload to assets/screenshots/02_demographics.png -->*

### Tenure & Loyalty

![Tenure & Loyalty Page](assets/screenshots/03_tenure.png)
*<!-- Upload to assets/screenshots/03_tenure.png -->*

### Services & Add-ons

![Services & Add-ons Page](assets/screenshots/04_services.png)
*<!-- Upload to assets/screenshots/04_services.png -->*

### Contract & Billing

![Contract & Billing Page](assets/screenshots/05_contract_billing.png)
*<!-- Upload to assets/screenshots/05_contract_billing.png -->*

### Charges & Revenue

![Charges & Revenue Page](assets/screenshots/06_charges_revenue.png)
*<!-- Upload to assets/screenshots/06_charges_revenue.png -->*

---

## Repository Structure

```
NexaLink-Churn-Analysis/
│
├── README.md
│
├── data/
│   ├── raw/
│   │   └── Customer_Churn_Dataset.xlsx
│   └── processed/
│       └── NexaLink_Churn_PowerBI.xlsx
│
├── dashboard/
│   └── NexaLink_Project.pbix
│
├── report/
│   └── NexaLink_Churn_Analysis_Report.pdf
│
└── assets/
└── screenshots/
├── 01_overview.png
├── 02_demographics.png
├── 03_tenure.png
├── 04_services.png
├── 05_contract_billing.png
├── 06_charges_revenue.png
└── 07_data_model.png
```

---

## How to Access the Dashboard

**View online:** Publish the `.pbip` project to Power BI Service to generate a shareable link.

**Open locally:**
1. Clone this repository
2. Open Power BI Desktop
3. Use **File → Open** and select `NexaLink Project.pbip`
4. The Excel data source must be at: `C:\Users\USER\Downloads\NexaLink_Churn_PowerBI.xlsx`
   - *Note: To run on a different machine, update the data source paths in Power Query (Transform Data → Data Source Settings)*

---

## Author

**Akinfisoye Erioluwa** — Data Analyst

[LinkedIn](https://www.linkedin.com/in/erioluwa-akinfisoye-30533a247/) | [GitHub](https://github.com/Eri-akinfisoye)

Specialising in customer analytics, churn analysis, and data-driven retention strategy using Power BI, Excel, and SQL
