
# Sales Summary Analysis using SQLite and Python

## Overview
This project performs a basic sales analysis using a small SQLite database and Python. It demonstrates how SQL queries can be embedded in Python to extract insights and visualize sales trends.

## Objectives
- Connect to a local SQLite database
- Run SQL queries to summarize sales by product and date
- Visualize revenue and quantity trends using matplotlib
- Explore product performance and daily sales patterns

## Tools Used
- Python (sqlite3, pandas, matplotlib)
- SQLite (embedded)
- Jupyter Notebook

## Dataset
The database `sales_data.db` contains a single table `sales` with the following columns:
- `product`: Name of the product
- `quantity`: Units sold
- `price`: Price per unit
- `date`: Date of sale

## Key SQL Queries
### 1. Revenue and Quantity by Product
```sql
SELECT 
    product, 
    SUM(quantity) AS total_qty, 
    SUM(quantity * price) AS revenue 
FROM sales 
GROUP BY product
ORDER BY revenue DESC
```

### 2. Daily Revenue Trend
```sql
SELECT 
    date,
    SUM(quantity * price) AS daily_revenue
FROM sales
GROUP BY date
ORDER BY date
```

### 3. Quantity Sold Over Time by Product
```sql
SELECT 
    date,
    product,
    SUM(quantity) AS qty
FROM sales
GROUP BY date, product
ORDER BY date
```

## Visualizations
- **Bar Chart**: Revenue by product
- **Line Chart**: Daily revenue trend
- **Pie Chart**: Revenue share by product
- **Stacked Bar Chart**: Quantity sold over time by product
- **Horizontal Bar Chart**: Total quantity sold

## Insights
- Laptops generated the highest revenue despite lower quantity sold.
- Phones had the highest sales volume.
- Jan 16 was the peak revenue day.
- Product mix varied across different sales dates.

## Folder Structure
```text
Sales-Summary-Analysis/
│
├── README.md
├── Sales_Summary.ipynb
├── Sales Summary Analysis using SQLite and Python.pdf
├── screenshots/
│   ├── revenue_trend.png
│   ├── stacked_bar.png
│   └── pie_chart.png
```

## How to Run
1. Clone the repository.
2. Open `Task7_Sales_Summary.ipynb` in Jupyter Notebook.
3. Ensure `sales_data.db` is located in the `data/` folder.
4. Run all cells to reproduce the analysis and charts.

## Author
Srusti  
August 14, 2025


