# 📊 Sales Analytics Dashboard using Power BI & SQL Server

## 🧾 Overview

This project demonstrates the creation of a dynamic and insightful **Sales Analytics Dashboard** using **Power BI** as the visualization tool and **SQL Server** as the backend database. It analyzes product performance, gross profits, revenue, and unit sales across countries and time periods.

The report was built for **Projectv1** and showcases real-time analytical capabilities, user interaction via slicers, and clean data modeling.

---

## 🛠 Tools & Technologies Used

- **Power BI Desktop**
- **SQL Server Management Studio**
- **DAX (Data Analysis Expressions)**
- **T-SQL (Transact-SQL)**
- **Data Modeling & Relationships**

---

## 🧱 Database Structure

The SQL database `ProductDB` contains multiple tables imported into Power BI using the **Import** mode.

### 🗂 Tables Used

| Table Name     | Description                                      |
|----------------|--------------------------------------------------|
| `Product`      | Product details including name, price, and color |
| `SubCategory`  | Classification of products                       |
| `Categories`   | Higher-level product category grouping           |
| `Sales`        | Detailed sales transaction data                  |
| `DateMaster`   | Date dimension table for time-based filtering    |
| `Geography`    | Country and town mapping                         |
| `Sales rep`    | Sales representatives and their IDs              |

---

## 🧾 SQL Setup (Sample Script)

```sql
CREATE TABLE Product (
    ProductID INT,
    SubCategoryKey INT,
    Color VARCHAR(50),
    ProductName VARCHAR(100),
    RetailPrice DECIMAL(10,2),
    StandardCost DECIMAL(10,2)
);

-- Sample Insert
INSERT INTO Product VALUES
(1, 3, 'Red', 'Alder', 23.95, 7.55),
(2, 2, 'Blue', 'Linder', 23.95, 7.55),
(3, 2, 'Green', 'Magnum', 23.95, 7.55),
...

---

## 🧠 Power BI Model
🔗 Data Relationships
All tables are connected using one-to-many and many-to-one relationships. Key relationships include:

Categories → SubCategory → Product → Sales

Sales → DateMaster, Geography, Sales rep

---

## 📅 Date Table (DAX)

DateMaster = CALENDAR(FIRSTDATE(Sales[Date]), LASTDATE(Sales[Date]))
Additional calculated columns like Month Name, Week Number, Weekday Name, and Quarter are included to enhance time-series visualizations.

---

## 📊 Report Features
✅ KPI Indicators
Total Revenue (2.18M)

Gross Profit (1.50M)

Units Sold (69K)

---

## 📌 Visualizations
Pie Chart: Revenue by SubCategory Name

Waterfall Chart: Year-wise Revenue Trends per Product

Matrix/Table: Product-wise revenue values

Slicers: Filter by Country, Year, and Month

---

## 📸 Screenshots
![Screenshot (1331)](https://github.com/user-attachments/assets/2efe3cfe-58d2-48ca-b66a-5ef8c32683df)

---

## 👨‍💻 Author
Pramoth Jayaprakash
🎓 Master’s in Applied Computer Science
