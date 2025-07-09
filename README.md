# Day 2 – SQL Joins Practice

## 📌 What are SQL Joins?

**Joins** are used to combine rows from two or more tables, based on a related column between them. They help retrieve meaningful combined data for analysis.

---

### 🔹 **Types of Joins, Theory, and Practice**

---

### 1. **INNER JOIN**

#### **Theory**
- Returns only rows that have **matching values in both tables**.
- Excludes records with no match.

**Example Use Case:**  
Retrieve a list of **orders along with customer names** where orders exist.

#### **Practice Query**

```sql
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
INNER JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
```

### 2. **LEFT JOIN (LEFT OUTER JOIN)**

#### **Theory**
Returns all rows from the left table, and **matched rows from the right table**.

If no match exists, result is NULL for right table columns.

**Example Use Case:**
List all customers, and if they have orders, show order details; else NULL.

#### **Practice Query**
```sql
Copy
Edit
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID;
```

**✅ Output: Displays all Customers, and their Order IDs if they have placed any orders.**

### **3. RIGHT JOIN (RIGHT OUTER JOIN)**
**Theory**
Returns all rows from the right table, and **matched rows from the left table**.

If no match exists, result is NULL for left table columns.

**Example Use Case:**
List all orders even if no matching customer data exists.

🔴 Note: SQLite (W3Schools Try-It) does not support RIGHT JOIN directly.

#### **Practice Query**
Using LEFT JOIN with tables reversed:

```sql
Copy
Edit
SELECT Orders.OrderID, Customers.CustomerName
FROM Orders
LEFT JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
```

**✅ Output: Displays all Orders with matching Customer Names (if any).**

### **4. FULL OUTER JOIN**

**Theory**
**Returns all rows from both tables**.

Shows NULL where there is no match in either table.

**Example Use Case:**
Retrieve all customers and all orders, matching where possible but showing all data regardless.

🔴 Note: SQLite does not support FULL OUTER JOIN directly. We simulate using UNION of LEFT JOIN and RIGHT JOIN.

#### **Practice Query**

```sql
Copy
Edit
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID

UNION

SELECT Customers.CustomerName, Orders.OrderID
FROM Orders
LEFT JOIN Customers
ON Orders.CustomerID = Customers.CustomerID;
```

**✅ Output: Combines results from both LEFT JOINs to mimic FULL OUTER JOIN behavior.**

### **🔑 Key Takeaways**
**INNER JOIN:** *Matching rows only*

**LEFT JOIN:** *All from left + matching right*

**RIGHT JOIN:** *All from right + matching left*

**FULL OUTER JOIN:** *All rows from both tables*

## 👩‍💻 Author

Vaishnavi Gopi

- [GitHub](https://github.com/VAISHNAVI-GOPI23)
- [LinkedIn](https://www.linkedin.com/in/vaishnavi-gopi23)


