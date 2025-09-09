# 🚀 Enterprise Sales & Inventory Management System (Oracle SQL End-to-End Project)

A **professional, production-grade Oracle SQL project** that simulates a real-world **Sales & Inventory Management System**.  
This project covers **Database Design, DML, Views, Triggers, Stored Procedures, Functions, ETL Simulation, Security, Optimization, and Analytics Reporting** — making it a **resume-ready end-to-end portfolio project**.

---

## 📂 Project Structure

- **Schema Design**: Customers, Products, Suppliers, Orders, Order Items, Employees, Payments, Shipments, Audit Log  
- **Sample Data**: Realistic inserts for suppliers, products, customers, employees, orders, and payments  
- **Business Logic**: Views, Triggers, Stored Procedures, Functions  
- **ETL Simulation**: Staging → Cleaning → Production load  
- **Security & Optimization**: Roles, Grants, Indexes, Partitioning  
- **Analytics & Reporting**: Advanced SQL queries for KPIs  

---

## 🛠️ Features

### 1. **Database Schema**
- 9 fully normalized tables with constraints & relationships.
- Foreign keys, check constraints, and identity columns.

### 2. **Business Logic**
- **Views**: Sales summary, Top Customers, Monthly Revenue, Employee Performance, Pending Shipments, Low Stock Alerts.  
- **Triggers**:  
  - Audit log (all changes to `ORDERS` are logged).  
  - Stock update (auto reduces product stock on new order).  
- **Procedures & Functions**:  
  - `sp_place_order` → End-to-end order placement workflow.  
  - `fn_customer_total_spent` → Total revenue from a customer.  
  - `fn_check_stock` → Check product availability.

### 3. **ETL Simulation**
- Raw **staging tables** (`STG_SALES_RAW`) for messy CSV data.  
- Transformation & cleaning into `STG_SALES_CLEAN`.  
- Automated **loading into production tables** with PL/SQL.

### 4. **Security & Optimization**
- Roles: `analyst_role` (read-only), `manager_role` (read/write).  
- Users with GRANT/REVOKE.  
- Indexes on high-usage columns for performance.  
- Example **range partitioning** for `ORDERS` by year.

### 5. **Analytics & Reporting**
- 📊 **Total Sales** by month & year.  
- 👑 **Top 5 Customers** by revenue.  
- 📉 **Low Stock** products report.  
- 👷 **Employee performance** by orders handled.  
- ⏱️ **Payment delays** (late or missing payments).

---

## 📊 ER Diagram
![ER Diagram](https://github.com/Sambie619/Enterprise-Sales-Inventory-Management-/blob/main/ERDiagram.png)  
*(Exported from dbdiagram.io / SQL Developer)*

---

## 🚀 Getting Started

### Prerequisites
- Oracle Database (Local or [Oracle LiveSQL](https://livesql.oracle.com/))  
- SQL Developer or DBeaver (optional for ERD visualization)

### Setup
1. Run [`Schema & Tables Creation.sql`](Schema%20&%20Tables%20Creation.sql) to create all tables and insert sample data.  
2. Run the provided scripts for views, triggers, procedures, and functions.  
3. Test queries using the analytics/reporting section.

---

## 📈 Sample Queries

### Total Monthly Revenue
```sql
SELECT TO_CHAR(payment_date, 'YYYY-MM') AS month,
       SUM(amount) AS total_sales
FROM PAYMENTS
GROUP BY TO_CHAR(payment_date, 'YYYY-MM')
ORDER BY month;

📌 Tech Highlights
 ✅ Oracle SQL / PL/SQL
 ✅ Triggers & Audit Logging
 ✅ ETL Pipeline Simulation
 ✅ User Roles & Security
 ✅ Analytics & Reporting

📷 Screenshots
   ER Diagram
📚 Future Enhancements
->  Add materialized views for faster reporting.
->  Integrate with Power BI / Tableau for dashboards.
->  Extend ETL with external table loading for large CSV files.

👨‍💻 Author
Sabin Shah
Contact:sabinshah619@gmail.com

🏷️ License
This project is licensed under the MIT License.
