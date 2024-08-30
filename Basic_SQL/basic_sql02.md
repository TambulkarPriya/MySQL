### Create Table

        CREATE TABLE Actors (
                Id INT AUTO_INCREMENT,
                FirstName VARCHAR(20) NOT NULL,
                SecondName VARCHAR(20) NOT NULL,
                DoB DATE NOT NULL,
                Gender ENUM('Male','Female','Other') NOT NULL,
                MaritalStatus ENUM('Married', 'Divorced', 'Single', 'Unknown') DEFAULT "Unknown",
                NetWorthInMillions DECIMAL NOT NULL,
                PRIMARY KEY (Id));

                OR

        CREATE TABLE IF NOT EXISTS Actors (
                Id INT AUTO_INCREMENT,
                FirstName VARCHAR(20) NOT NULL,
                SecondName VARCHAR(20) NOT NULL,
                DoB DATE NOT NULL,
                Gender ENUM('Male','Female','Other') NOT NULL,
                MaritalStatus ENUM('Married', 'Divorced', 'Single', 'Unknown') DEFAULT "Unknown",
                NetWorthInMillions DECIMAL NOT NULL,
                PRIMARY KEY (Id));

* AUTO_INCREMENT - AUTO_INCREMENT is a column attribute used with integer types to automatically generate a unique identifier for new rows inserted into a table. This is often used for primary key columns to ensure that each row has a unique ID.

* How AUTO_INCREMENT Works - 
            1. Column Type: It must be used with an integer data type like INT, BIGINT, TINYINT, etc.
            2. Automatic Increment: When you insert a new row into the table, MySQL automatically assigns the next number in the sequence to the AUTO_INCREMENT column.
            3. Starting Value: By default, the starting value is 1, and it increments by 1 for each new row. However, you can change the starting value using the AUTO_INCREMENT table option.

* Example:-
             CREATE TABLE employees (
                    id INT AUTO_INCREMENT,
                    first_name VARCHAR(50),
                    last_name VARCHAR(50),
                    PRIMARY KEY (id)
                );

* Changing the Starting Value:-
            You can change the starting value like this:

            ALTER TABLE employees AUTO_INCREMENT = 100;

* Considerations:-
         1. The AUTO_INCREMENT value continues to increase even if rows are deleted.
         2. If you insert a row with a specific id, the next AUTO_INCREMENT value will be higher than the manually inserted id.

### NOT NULL:-
            In MySQL, the NOT NULL constraint is used to ensure that a column cannot have a NULL value. When you define a column with the NOT NULL constraint, MySQL will enforce that every row in the table must have a value for that column; if you try to insert or update a row without providing a value for that column, MySQL will generate an error.

* Key Points About NOT NULL:-
1. Data Integrity: Ensures that critical columns (e.g., username, email) always have a value.
2. Default Values: If you don't provide a value for a NOT NULL column, you must explicitly define a default value if you want MySQL to automatically insert something.
3. Performance: In some cases, NOT NULL columns can lead to better performance since MySQL doesn't have to check for NULL values.

* Adding NOT NULL to an Existing Column:- 
           You can also add the NOT NULL constraint to an existing column using an ALTER TABLE statement:
           
           ALTER TABLE Users MODIFY Username VARCHAR(255) NOT NULL;


* Removing NOT NULL Constraint:-
           To remove the NOT NULL constraint from a column:

           ALTER TABLE Users MODIFY Username VARCHAR(255);

* DESC command:-
1. To Describe the Structure of a Table:
* The DESC (or DESCRIBE) command is used to display the structure of a table. It provides information about the columns, their data types, whether they can hold NULL values, and other details like key constraints and default values.

          DESC table_name;

This would display the structure of the Users table, showing details like column names, data types, NULL or NOT NULL constraints, PRIMARY KEY status, etc.

2. To Specify Sorting Order in a Query:
* The DESC keyword can also be used in the ORDER BY clause of a SELECT query to sort the results in descending order.

          SELECT column1, column2 
            FROM table_name
            ORDER BY column_name DESC;
