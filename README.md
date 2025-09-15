# Telco Customer Retention & Churn Analysis

Customer churn—the rate at which subscribers cancel their service—directly impacts recurring revenue.
This project explores a telecom churn dataset to uncover churn patterns, estimate revenue loss,
and identify drivers of customer retention using **SQLite** and **Python (pandas, matplotlib, seaborn)**.

---

## 1. Project Overview
- **Business Context**  
  A telecom company wants to understand why customers leave (“churn”) and how to reduce it.
- **Goal**  
  Clean the raw Telco churn dataset, create a SQLite database, and perform intermediate–advanced SQL queries
  to reveal churn drivers and revenue impacts.
- **Deliverables**  
  - `data/telco_churn.db` – SQLite database ready for analysis  
  - `Telco_Customer_Churn.ipynb` – Jupyter notebook with cleaning, SQL analysis, and visualizations  
  - `data/cleaned_telco.csv` – cleaned dataset

---

## 2. Repository Structure

```
telco-churn-sql-analysis/
│
├─ Telco_Customer_Churn.ipynb   # main analysis notebook
├─ telco_churn.db               # SQLite database
├─ README.md
└─ data/
   ├─ Telco_Customer_Churn.csv  # original raw dataset
   └─ cleaned_telco.csv         # cleaned dataset

```
---

## 3. Data Source
- **Original File:** Telco_Customer_Churn.csv  
- **Key Columns:**  
  `customerID`, `gender`, `SeniorCitizen`, `Partner`, `Dependents`, `tenure`,  
  `Contract`, `InternetService`, `PaymentMethod`, `MonthlyCharges`, `TotalCharges`, `Churn`

---

## 4. Data Cleaning
- Converted **TotalCharges** from text to numeric and handled blank values (customers with zero tenure).
- Dropped unnecessary columns and ensured correct data types.
- Exported a cleaned dataset (`cleaned_telco.csv`) and loaded it into SQLite as table **Customers**.

---

## 5. SQL Analysis
The project demonstrates intermediate and advanced SQL techniques:

| Technique | Example |
|-----------|--------|
| Aggregation & Grouping | Calculate churn rate and average monthly charges |
| Window Functions | Rank highest lifetime value churned customers |
| Common Table Expressions (CTEs) | Segment customers by churn risk |
| Views | Create reusable churn summary (`v_ChurnSummary`) |

Questions answered include:
1. What is the overall churn rate and monthly revenue lost?
2. How does contract type affect churn and monthly charges?
3. Which internet service type has the highest churn rate?
4. Which customer segments present the highest churn risk?

---

## 6. Visualizations
The notebook includes Python visualizations to complement SQL queries:
- **Churn Distribution:** bar chart of churn vs. retained customers
- **Average Monthly Charge by Contract:** compare contract types
- **Churn Rate by Internet Service:** identify services with highest churn

---

## 7. Key Insights
- Overall churn rate is about **26.5%** (1,869 of 7,043 customers).
- Churned customers represent roughly **$139k** in lost monthly revenue.
- **Month-to-month contracts** have the highest churn and highest monthly charges.
- **Fiber optic** users churn at more than twice the rate of DSL users.
- **Two-year contracts** show very low churn (<2%) and longest customer tenure.

---

## 8. Requirements
Install dependencies:
pip install pandas matplotlib seaborn
(SQLite is included with Python.)

---

## 9. How to Reproduce
1. Clone this repository:
   ```bash
   git clone https://github.com/nnguyen79pine/telco-churn-sql-analysis.git
   cd telco-churn-sql-analysis
2. Launch Jupyter Lab or Notebook:
jupyter lab
3. Open Telco_Customer_Churn.ipynb and run all cells to:
- Clean the raw dataset
- Create the SQLite database
- Execute SQL queries
- Generate visualizations

## 10. Notes

- .ipynb_checkpoints/ is excluded from version control; these are automatic Jupyter backups.

- The database file (telco_churn.db) is provided for convenience;
the notebook can rebuild it from the CSV if removed.

## 11. License
MIT License – feel free to use this project for learning or portfolio purposes.

