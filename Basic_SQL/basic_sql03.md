### Temporary Table:- 
        A temporary table in MySQL is a type of table that exists only during the session in which it was created. It is automatically deleted when the session ends, which means that temporary tables are useful for storing intermediate results or for working with data in a way that doesn’t affect the permanent database tables.

* Temporary tables can be used to work with intermediate data or results. Also, complex queries with joins or nested queries can be broken up and worked on step-by-step by storing intermediate results in temporary tables.

##### Key Features of Temporary Tables:-
1. Session-Specific: The table is only available to the session that created it. No other session can see it.
2. Automatic Deletion: It is dropped automatically when the session ends or explicitly using the DROP TABLE command.
3. Same Name as Regular Tables: A temporary table can have the same name as a regular table, and within the same session, the temporary table will be prioritized.

* Syntax:-
                   CREATE TEMPORARY TABLE temp_table_name (
                            column1 datatype,
                            column2 datatype,
                            ...
                        );

* Example:- 
                    CREATE TEMPORARY TABLE temp_orders (
                            order_id INT,
                            product_name VARCHAR(100),
                            quantity INT
                        );

                    INSERT INTO temp_orders (order_id, product_name, quantity)
                    VALUES (1, 'Laptop', 2), (2, 'Mouse', 10);

                    SELECT * FROM temp_orders;

#### SHOW CHARACTER SET:-
      The SHOW CHARACTER SET command in MySQL is used to display all the available character sets supported by the MySQL server. A character set in MySQL is a set of symbols and encodings used to store and retrieve string data. Each character set in MySQL has a default collation, which determines the rules for comparing characters within that character set.

* Syntax:- SHOW CHARACTER SET;

* Output Explanation:- 
When you run the SHOW CHARACTER SET command, the output includes the following columns:
1. Charset: The name of the character set.
2. Description: A brief description of the character set.
3. Default collation: The default collation associated with the character set.
4. Maxlen: The maximum number of bytes required to store one character in the character set.

* Use Cases:-
1. Choosing a Character Set: When creating tables or columns, you can use this command to decide which character set is most appropriate for your data.
2. Checking Available Character Sets: To ensure that the server supports the character set you want to use.

#### Example Use in Creating a Table:

                CREATE TABLE example_table (
                    name VARCHAR(100)
                ) CHARACTER SET utf8mb4;


#### SHOW COLLECTION:-
        The SHOW COLLATION command in MySQL is used to display all the available collations supported by the MySQL server. A collation in MySQL determines how string comparison is performed for a particular character set. Each character set can have multiple collations, which define different sorting and comparison rules.

* Output Explanation:-
When you execute the SHOW COLLATION command, the output includes the following columns:
1. Collation: The name of the collation.
2. Charset: The character set associated with the collation.
3. Id: The internal ID used by MySQL for the collation.
4. Default: Indicates whether this is the default collation for the character set (Yes or No).
5. Compiled: Whether the collation is compiled into the MySQL server (Yes or No).
6. Sortlen: The length of the sort order used by the collation.             

* Explanation:-
1. armscii8_bin: A binary collation for the armscii8 character set, not the default collation.
2. armscii8_general_ci: The default collation for the armscii8 character set, which is case-insensitive (ci).
3. ascii_bin: A binary collation for the ascii character set.
4. ascii_general_ci: The default collation for the ascii character set.
5. big5_bin: A binary collation for the big5 character set.
6. big5_chinese_ci: The default collation for the big5 character set, which is case-insensitive and designed for sorting Chinese characters.

* Use Cases:-
1. Choosing a Collation: Use this command to find the available collations for a specific character set, helping you decide which one to use based on your sorting and comparison requirements.
2. Checking Default Collations: Identify the default collation for a particular character set when creating tables or columns.
3. Optimizing Queries: Collations can affect the performance of queries, so understanding which collation to use can help optimize string comparisons and sorting.

#### Example Use in Creating a Table:-
CREATE TABLE example_table (
    name VARCHAR(100)
) CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;


* Filtering Results:-
SHOW COLLATION LIKE 'utf8mb4%';

* SHOW VARIABLES LIKE "c%";
