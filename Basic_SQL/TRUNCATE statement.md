### TRUNCATE statement:-
      In MySQL, the TRUNCATE statement is used to delete all rows from a table, similar to the DELETE statement without a WHERE clause. However, TRUNCATE is faster and has some differences in behavior compared to DELETE.

### Syntax:-
                  TRUNCATE TABLE table_name;

### Key Differences Between TRUNCATE and DELETE:-

1. Speed:-
TRUNCATE is faster because it drops and recreates the table, rather than deleting each row individually like DELETE.

2. Resetting Auto-Increment:-
TRUNCATE resets any AUTO_INCREMENT counters for the table, so the next insert will start from 1 again (or the seed value).
DELETE does not reset the AUTO_INCREMENT value unless explicitly done.

3. Cannot Use WHERE Clause:-
TRUNCATE removes all rows without the option of filtering them like you can with DELETE using a WHERE clause.

4. Transactions:-
TRUNCATE is not transactional, so it cannot be rolled back if you are using transactional storage engines (like InnoDB), whereas DELETE can be rolled back within a transaction.


#### Important Notes:-

1. You cannot TRUNCATE a table that is referenced by a foreign key constraint in InnoDB.
2. Be cautious when using TRUNCATE because it will delete all data without the ability to specify conditions or recover it easily.
