### Where Clause:-
                 The WHERE clause in MySQL is used to filter records that meet a certain condition. It is commonly used in SELECT, UPDATE, DELETE, and other SQL statements to specify which rows should be affected by the query.

* Basic Syntax:-
               SELECT column1, column2, ...
               FROM table_name
               WHERE condition;

* Examples:-
1. Selecting specific rows:
              
              SELECT * FROM employees
              WHERE department = 'Sales';

2. Using comparison operators:
 
              SELECT * FROM orders
              WHERE order_date >= '2024-01-01';

3. Combining conditions with AND/OR:
 
              SELECT * FROM products
              WHERE price > 100 AND stock > 50;

4. Using IN and BETWEEN:
 
              SELECT * FROM customers
              WHERE country IN ('USA', 'Canada', 'UK');

             SELECT * FROM sales
             WHERE sale_date BETWEEN '2024-01-01' AND '2024-01-31';

In Above examples we used:
 1. Comparison Operators: =, !=, >, <, >=, <=
 2. Logical Operators: AND, OR, NOT
 3. Pattern Matching: LIKE, RLIKE
 4. Range and Set: BETWEEN, IN