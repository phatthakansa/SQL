# 📊 SQL Practice – Basic Query Examples

This project contains solutions to basic SQL query exercises involving customer and product data.  
The queries demonstrate the use of **SELECT**, **WHERE**, **JOIN**, and **YEAR()** functions for retrieving data from multiple related tables.

---

## 📝 SQL Structure
![image](https://github.com/user-attachments/assets/1d5ba39a-a804-4480-b541-2749860f0846)

### Display all product names from the `Products` table
![image](https://github.com/user-attachments/assets/381bab52-e186-4f11-991e-d5ef7adfd6e9)
> **SQL:**
```sql
SELECT product_name
FROM products;
```
Explanation:
This query selects all product names from the products table using a simple SELECT statement.

---

### Display the id, name, and citizen of customers who registered in 2022
![image](https://github.com/user-attachments/assets/f04cf4d3-3019-4b32-9687-e4a50b8d4532)

> **SQL:**
```sql
SELECT id, name, citizen
FROM Customers
WHERE YEAR(registered_date) = 2022;
```
Explanation:
We use the YEAR() function to filter customers who registered in the year 2022.

---

### Display product ID, product name, customer's full name, and citizen where customer_id = '001110001'
![image](https://github.com/user-attachments/assets/05e2c1ec-0f4a-45d3-93d9-a8e8e79ab5c6)


> **SQL:**
```sql
SELECT p.product_id, p.product_name, c.full_name, c.citizen
FROM Products p
JOIN Orders o ON p.product_id = o.product_id
JOIN Customers c ON o.customer_id = c.customer_id
WHERE c.customer_id = '001110001';
```
Explanation:
This query joins the Products, Orders, and Customers tables to get detailed product and customer information for a specific customer ID.
