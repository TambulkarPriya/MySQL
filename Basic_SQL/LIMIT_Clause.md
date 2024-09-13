### LIMIT clause:-
       The LIMIT clause in MySQL is used to specify the number of records to return from a query. It is particularly useful for paginating results or limiting large datasets. You can also use the OFFSET option to skip a specific number of records before starting to return rows.

#### Syntax:-
            SELECT column1, column2, ...
            FROM table_name
            LIMIT number_of_rows OFFSET skip_rows;

* Example 1: Fetch the first 10 records
            
            SELECT * FROM employees
            LIMIT 10;

* Example 2: Fetch 5 records, starting from the 6th row
             
             SELECT * FROM employees
             LIMIT 5 OFFSET 5;
The above query will skip the first 5 records and return the next 5, i.e., rows 6 to 10.

* Example 3: Fetch the top 5 highest salaries
               
                SELECT name, salary
                FROM employees
                ORDER BY salary DESC
                LIMIT 5;


* In MySQL, LIMIT is highly useful for efficiently managing large datasets, especially when combined with ORDER BY and pagination strategies.


