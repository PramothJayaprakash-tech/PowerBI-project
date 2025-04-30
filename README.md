# 🚀 Advanced Sales Analytics Dashboard | Power BI + SQL Server Integration

## 📌 Project Overview

This project presents a **fully interactive and visually rich Sales Analytics Dashboard** created using **Power BI** with a backend integration to **SQL Server**. It provides in-depth insights into product-wise performance, gross profit, total revenue, and sales units across multiple geographies and time frames.

Built as part of **Projectv1**, this dashboard leverages data modeling, DAX measures, slicer-based interactivity, and clean visualization design to deliver an intuitive and business-ready analytical solution.

---

## 🛠 Tools & Technologies Used

- **Power BI Desktop**
- **Microsoft SQL Server Management Studio**
- **DAX (Data Analysis Expressions)**
- **T-SQL (Transact-SQL)**
- **Dimensional Data Modeling**
- **Interactive Visualizations & Slicers**

---

## 🧱 Database Design

The data is sourced from a custom-built SQL Server database called `ProductDB`. The tables were cleaned, imported, and related using star schema design principles.

### 📋 Tables in Use

| Table Name     | Purpose                                               |
|----------------|--------------------------------------------------------|
| `Product`      | Stores product name, color, subcategory, price & cost |
| `SubCategory`  | Groups products into subcategories                    |
| `Categories`   | Higher-level classification of subcategories          |
| `Sales`        | Detailed transaction data across time & location      |
| `DateMaster`   | Custom calendar table used for time intelligence      |
| `Geography`    | Country and city mapping                              |
| `Sales rep`    | Sales representative information                      |

---

## 🧾 SQL Sample: Product Table Creation

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
(4, 1, 'Red', 'Quad', 43.95, 13.75),
(5, 1, 'Blue', 'Black Monk', 43.95, 13.75);


## 🧠 Power BI Data Model
🔗 Key Relationships
All tables are connected using one-to-many relationships to enable efficient filtering and aggregation:

Categories → SubCategory → Product → Sales

Sales → DateMaster, Geography, Sales rep


---


##📅 Date Table (DAX)
A custom date dimension was generated using the following DAX formula:

DateMaster = CALENDAR(FIRSTDATE(Sales[Date]), LASTDATE(Sales[Date]))
Additional calculated columns like Month Name, Quarter, Week Day, and Month Order were added for advanced time-series filtering and visual clarity.

##📊 Key Dashboard Features
✅ KPI Cards
Total Revenue: 2.18M

Gross Profit: 1.50M

Units Sold: 69K

## 📌 Visualizations
Pie Chart: Distribution of Revenue by SubCategory

Waterfall Chart: Year-over-Year Product Revenue Trends

Matrix Table: Product-wise Revenue Values

Slicers: Country, Year, and Month filters for user interactivity

## 📸 Screenshots

![Screenshot (1331)](https://github.com/user-attachments/assets/9a604e61-ba09-4dab-980f-af7d6c04180e)


📈 What I Learned / Did
Designed a star schema model and implemented proper relationships.

Built a custom calendar with dynamic DAX fields for slicing and time-based trends.

Wrote SQL scripts to generate and populate source data.

Developed calculated columns, measures, and KPIs in DAX.

Crafted visually engaging and business-ready dashboards.

👨‍💻 Author
Pramoth Jayaprakash
🎓 Master's in Applied Computer Science

