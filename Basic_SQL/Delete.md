#### DELETE:-
      In MySQL, the DELETE statement is used to remove rows from a table based on a specified condition.

### Syntax:-
      DELETE FROM table_name WHERE condition;

* table_name: The name of the table from which you want to delete data.
* condition: A condition that determines which rows should be deleted. If no condition is provided, all rows will be deleted, which can be dangerous, so always use a condition unless you're sure you want to delete everything.

1. Example 1: Delete specific rows
  
              DELETE FROM employees WHERE employee_id = 101;

2. Example 2: Delete all rows (be cautious)

              DELETE FROM employees;

3. Example 3: Delete multiple rows

              DELETE FROM employees WHERE department = 'HR';

4.            DELETE FROM employees WHERE department = 'Sales' LIMIT 5;






