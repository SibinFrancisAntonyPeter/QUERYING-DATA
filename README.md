# QUERYING-DATA
CREATE TABLE Country (
Id INT PRIMARY KEY,
Country_name VARCHAR(50),
Population INT,
Area VARCHAR(50)
);

CREATE TABLE Persons (
Id INT PRIMARY KEY,
Fname VARCHAR(30),
Lname VARCHAR(30),
Population INT,
Rating FLOAT,
Country_Id INT,
Country_name VARCHAR(50)
);


INSERT INTO Country (Id, Country_name, Population, Area) VALUES 
(1, 'USA', 331000000, 'California'),
(2, 'India', 1380000000, 'Maharashtra'),
(3, 'Canada', 38000000, 'Ontario'),
(4, 'Australia', 25600000, 'New South Wales'),
(5, 'UK', 67000000, 'London'),
(6, 'Germany', 83000000, 'Bavaria'),
(7, 'France', 67000000, 'Île-de-France'),
(8, 'Japan', 125000000, 'Tokyo'),
(9, 'Brazil', 213000000, 'São Paulo'),
(10, 'South Africa', 60000000, 'Gauteng');

INSERT INTO Persons (Id, Fname, Lname, Population, Rating, Country_Id, Country_name)
VALUES 
(1, 'John', 'Doe', 1000000, 4.5, 1, 'USA'),
(2, 'Jane', 'Smith', 2000000, 4.8, 2, 'India'),
(3, 'Michael', 'Brown', 1500000, 4.2, 3, 'Canada'),
(4, 'Emily', 'Davis', 2500000, 3.9, 4, 'Australia'),
(5, 'James', 'Wilson', 1800000, 4.0, 5, 'UK'),
(6, 'Anna', 'Moore', 1300000, 4.6, 6, 'Germany'),
(7, 'Robert', 'Taylor', 1700000, 3.7, 7, 'France'),
(8, 'Linda', 'Anderson', 1400000, 4.9, 8, 'Japan'),
(9, 'David', 'Thomas', 2100000, 3.8, 9, 'Brazil'),
(10, 'Sarah', 'Jackson', 1600000, 4.3, 10, 'South Africa');

SELECT * FROM Country;
SELECT * FROM Persons;


 # 1)List the distinct country names from the Persons table 
 
 SELECT DISTINCT Country_name FROM Persons;
 
 # 2)Select first names and last names from the Persons table with aliases
 
 SELECT Fname AS FirstName, Lname AS LastName FROM Persons;

# 3)Find all persons with a rating greater than 4.0. 

SELECT * FROM Persons WHERE Rating > 4.0;

# 4)Find countries with a population greater than 10 lakhs.

SELECT * FROM Country WHERE Population > 1000000 ;

# 5)Find persons who are from 'USA' or have a rating greater than 4.5.

SELECT * FROM Persons WHERE Country_name = 'USA' OR Rating > 4.5;

# 6)Find all persons where the country name is NULL.

SELECT * FROM Persons WHERE Country_name = 'NULL';

# 7)Find all persons from the countries 'USA', 'Canada', and 'UK'. 

SELECT * FROM Persons WHERE Country_name IN('USA', 'Canada','UK');

# 8)Find all persons not from the countries 'India' and 'Australia'. 

SELECT * FROM Persons WHERE Country_name NOT IN ('India','Australia');

# 9)Find all countries with a population between 5 lakhs and 20 lakhs.

SELECT * FROM Country WHERE Population BETWEEN 500000 AND 1000000;

# 10)Find all countries whose names do not start with 'C'.

SELECT * FROM Country WHERE Country_name NOT LIKE 'C%';

