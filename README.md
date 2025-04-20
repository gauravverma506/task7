# ASK 7: Get Basic Sales Summary from a Tiny SQLite Database using Python

## Objective
Use SQL inside Python to pull simple sales information (like total quantity sold and total revenue), and display the results using print statements and a simple bar chart.

---

## Tools Used
- *Python*
- *SQLite* (sqlite3 - built into Python)
- *Pandas*
- *Matplotlib*

---

## Dataset
- SQLite database file: sales_data.db
- Contains a single table: sales with fields like:
  - item (product name)
  - quantity
  - price_per_unit
  - total_amount (used directly for revenue)

---

## Deliverables
- A Python script (sales_summary.py) that:
  1. Connects to sales_data.db
  2. Runs SQL queries to get:
     - Total quantity sold per product
     - Total revenue per product
  3. Loads results into a pandas DataFrame
  4. Prints the result
  5. Plots a simple bar chart using matplotlib
  6. Saves the chart as sales_chart.png

---

## Sample SQL Query Used
```sql
SELECT item AS product, 
       SUM(quantity) AS total_qty, 
       SUM(total_amount) AS revenue 
FROM sales 
GROUP BY item;
