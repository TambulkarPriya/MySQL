###### In this file we will see/write/use some basic commands related to DATABASE.

1. To check available databases in system.
        
        SHOW DATABASES;
          
2. The USE database_name command in MySQL is used to select a specific database that you want to work with in your current session. Once you execute this command, all subsequent SQL queries will be run against the selected database until you switch to another database using the USE command again or end the session.

        USE mysql;  ---- Here USE is command and mysql is database name.

3. The SHOW CREATE DATABASE command in MySQL is used to display the SQL statement that was used to create a specific database, including any options that were set during its creation, such as the character set and collation.
  
        SHOW CREATE DATABASE database_name;

Here - database_name: Replace this with the name of the database you want to see the creation statement for. And the output will show the CREATE DATABASE statement with the character set, collation, and any other attributes that were specified when the database was created.
        
        show create database mysql;

4. The SHOW TABLES command in MySQL is used to list all the tables in the currently selected database. This command is helpful for quickly viewing all the tables within a specific database.

        SHOW TABLES;

5. We can also explore the structure of a table using the DESCRIBE command. 
        
        DESCRIBE tableName;

6. We can also use the SHOW statement to display how the table was created.

        SHOW CREATE TABLE tableName;

7. We can display the column information for a table using the SHOW statement.
        
        SHOW COLUMNS FROM tableName;

8. To check which database you are currently working in within a MySQL session.
 
        SELECT DATABASE();
Here - DATABASE() is a built-in MySQL function that returns the name of the database that is currently selected in your session. And If no database is selected, it will return NULL.

9. We can delete the database using the DROP command.

        DROP database databaseName;

10. Command to create database.

        CREATE DATABASE databaseName;
      
                OR

        CREATE DATABASE IF NOT EXISTS databaseName;   --- Here IF NOT EXISTS clause is useful when writing a script that may be invoked or run  repeatedly and will abort when creating a database that already exist.


11. For MySQL datatypes you can visit: https://www.w3schools.com/mysql/mysql_datatypes.asp

12. ENUM data type: The ENUM data type in MySQL is a string object that allows you to define a column with a predefined set of allowed values. Each value in the ENUM list is assigned an index, and only one of these values can be stored in the column for each row. It is often used to represent categorical data, where the possible values are known and fixed.
      
      * Characteristics of ENUM:-
           1. Predefined List: You define the set of possible values when you create the table, and only these values (or NULL) can be stored in the column.
           2. Single Value: Each field in an ENUM column can only hold one of the specified values.
           3. Storage: Internally, MySQL stores ENUM values as integer indexes representing the position of the value in the list. For example, the first value is stored as 1, the second as 2, and so on.

     * Syntax:-
                CREATE TABLE table_name (
                        column_name ENUM('value1', 'value2', 'value3', ...)
                    );

     * Example:-
            Let's say you want to create a table to store information about employees, including their job type, which can only be one of the following: 'Manager', 'Developer', 'Designer', or 'Intern'
     
            CREATE TABLE employees (
                id INT AUTO_INCREMENT PRIMARY KEY,
                name VARCHAR(100),
                job_title ENUM('Manager', 'Developer', 'Designer', 'Intern')
            );

     * Inserting Data:-

                INSERT INTO employees (name, job_title) VALUES ('Alice', 'Developer');
                INSERT INTO employees (name, job_title) VALUES ('Bob', 'Manager');

     * Retrieving Data:-
               
               SELECT name, job_title FROM employees;
      
     * Benefits:-
           1. Data Integrity: Ensures that only valid, predefined values are stored in the column, reducing the risk of invalid data.
           2. Efficiency: Because ENUM values are stored as integers, they are more storage-efficient than storing the equivalent strings directly.

     * Limitations:-
           1. Inflexibility: If you need to add or modify the list of allowed values, you'll need to alter the table structure, which may require careful management in a production environment.
           2. Limited Use Cases: ENUM is most useful for fields where the set of possible values is small and do not require to change frequently.

      * Modifying ENUM Values:-
           If you need to add, remove, or change the allowed values in an ENUM column, you can use the ALTER TABLE command:

           Example:- 
                      ALTER TABLE employees MODIFY COLUMN job_title ENUM('Manager', 'Developer','Designer', 'Intern', 'HR');

        In this example, the value 'HR' was added to the ENUM list.
