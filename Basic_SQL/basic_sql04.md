# Insert query

1.      INSERT INTO Actors ( 
                FirstName, SecondName, DoB, Gender, MaritalStatus, NetworthInMillions) 
                VALUES ("Brad", "Pitt", "1963-12-18", "Male", "Single", 240.00);

2.      INSERT INTO Actors ( 
                FirstName, SecondName, DoB, Gender, MaritalStatus, NetworthInMillions) 
                VALUES 
                ("Jennifer", "Aniston", "1969-11-02", "Female", "Single", 240.00),
                ("Angelina", "Jolie", "1975-06-04", "Female", "Single", 100.00),
                ("Johnny", "Depp", "1963-06-09", "Male", "Single", 200.00);

3.      INSERT INTO Actors 
                VALUES (DEFAULT, "Dream", "Actress", "9999-01-01", "Female", "Single", 000.00);

4.      INSERT INTO Actors VALUES (NULL, "Reclusive", "Actor", "1980-01-01", "Male", "Single", DEFAULT);

5.      INSERT INTO Actors () VALUES ();

6.      INSERT INTO Actors SET DoB="1950-12-12", FirstName="Rajnikanth", SecondName="",  Gender="Male", NetWorthInMillions=50,  MaritalStatus="Married";

