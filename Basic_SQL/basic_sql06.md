# ORDER BY clause:- 
        ORDER BY clause is followed by the column name on which we intend to sort. This column is called the sort key. By default, the sorting is case-insensitive and in ascending order. Sorting of string columns depends on the character set being used and the collation order.

#### Syntax:-
                 SELECT col1, col2, … coln

                FROM table

                WHERE col3 LIKE "%some-string%"

                ORDER BY col3


#### Examples:-

                -- Query 1
                SELECT * FROM Actors ORDER BY FirstName;

                -- Query 2
                SELECT * FROM Actors ORDER BY FirstName DESC;

                -- Query 3
                SELECT * FROM Actors ORDER BY NetWorthInMillions, FirstName;

                -- Query 4
                SELECT * FROM Actors ORDER BY NetWorthInMillions, SecondName;

                -- Query 5
                SELECT * FROM Actors ORDER BY NetWorthInMillions DESC, FirstName ASC;

                -- Query 6
                SELECT * FROM Actors ORDER BY NetWorthInMillions DESC, FirstName DESC;

                -- Query 7
                SELECT * FROM Actors ORDER BY BINARY FirstName;

                -- Query 8
                SELECT * FROM Actors ORDER BY NetWorthInMillions;

                -- Query 9
                SELECT * FROM Actors ORDER BY CAST(NetWorthInMillions AS CHAR);
