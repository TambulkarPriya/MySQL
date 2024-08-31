#### Like Operator:-
                 The LIKE operator in MySQL is used to search for a specified pattern in a column. It is often used in SELECT statements to filter rows that match a particular pattern in a string column.

* Basic Syntax:- 
                        SELECT column1, column2, ...
                        FROM table_name
                        WHERE column LIKE pattern;

## Wildcards Used with LIKE:-
  * %: Represents zero, One or more characters.
  * _: Represents a single character.

## Examples:-
* Matching patterns with %:

1. This query retrieves all employees whose first name starts with the letter 'J'.
                    
                    SELECT * FROM employees
                    WHERE first_name LIKE 'J%';

2. This query retrieves all products whose names end with 'Book'.

                    SELECT * FROM products
                    WHERE product_name LIKE '%Book';

3. This query retrieves all customers who have a Gmail address.

                    SELECT * FROM customers
                    WHERE email LIKE '%@gmail.com';

* Matching patterns with _:-

1. This query retrieves all employees whose first name has 'a' as the second character.
             
                    SELECT * FROM employees
                    WHERE first_name LIKE '_a%';

2. This query retrieves all products with a code like 'A' followed by any character, followed by '1'.

                    SELECT * FROM products
                    WHERE product_code LIKE 'A_1';

* Combining % and _:-

This query retrieves all employees whose first name has 'a' as the second character and ends with 'y'.

                    SELECT * FROM employees
                    WHERE first_name LIKE '_a%y';

### Case Sensitivity:-

1. Default Behavior: The LIKE operator is case-insensitive in MySQL by default, meaning LIKE 'a%' will match both 'Alice' and 'alice'.
2. Case-Sensitive Matching: To perform a case-sensitive search, you can use the BINARY keyword

                    SELECT * FROM employees
                    WHERE BINARY first_name LIKE 'A%';

### Key Points:-
1. Use LIKE for pattern matching in text columns.
2. % matches any sequence of characters (including an empty sequence).
3. _ matches exactly one character.
4. BINARY can be used for case-sensitive matching.



