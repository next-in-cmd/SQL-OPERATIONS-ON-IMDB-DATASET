# SQL-OPERATIONS-ON-IMDB-DATASET 
Performed SQL operation on the IMDB dataset for practicing SQL query operations and building database-driven applications. It represents a structured collection of data about movies, actors, directors, ratings, and other related information.

** SELECT QUERY:** A SELECT query in SQL is a command used to retrieve data from one or more tables in a database. 

                    SELECT * FROM movies; '*' defines that set of all rows with column names. 
                    SELECT name,rankscore FROM movies; 
                       
**LIMIT:** The LIMIT clause in SQL is used to specify the maximum number of rows to be returned in the result set of a query. 

                    SELECT name,year FROM movies LIMIT 20;
                     
**OFFSET:** The OFFSET clause in SQL is used to specify the number of rows to skip before starting to return rows from a query.

                    SELECT name,rankscore FROM movies LIMIT 20 OFFSET 20;        
                     
**ORDER BY:** The ORDER BY clause in SQL is used to sort the result set of a query in either ascending (default) or descending order based on one or more columns. 

                    SELECT name,year FROM directors ORDER BY year DESC LIMIT 20; 
Here in order by clause 'ASC' is by default used by query optimiser if 'DESC' is not specified 

                    SELECT name,year FROM directors ORDER BY LIMIT 20; 

**DISTINCT:** The DISTINCT keyword in SQL is used to retrieve unique values from a column or combination of columns in a query. It ensures that duplicate rows in the result 
              set are eliminated, leaving only distinct rows. 
              
                    SELECT DISTINCT genre FROM movies_genres; 
                    SELECT DISTINCT first_name,last_name FROM directors ORDER BY first_name;  
**WHERE:** WHERE clause is used to filter records in a query based on specific conditions. It is typically used in SELECT, UPDATE, DELETE, and INSERT statements to specify which rows should be affected by the query. 

                    SELECT name,year,rankscore FROM movies WHERE rankscore>9; 
                    SELECT name,year,rankscore FROM movies WHERE rankscore>9 ORDER BY rankscore DESC LIMIT 20; 

WHERE clause is consist of Comparison operator like =, <>, !=, >, <, >=, <=. 

 **NULL defines does not exist/missing/unknown** 
'=' does not work with NULL operations. 

                    SELECT name,year,rankscore FROM movies WHERE rankscore = NULL; 
                    
TO work with NULL operations Keywords[IS NULL/IS NOT NULL] are used. 

                    SELECT name,year,rankscore FROM movies WHERE rankscore IS NULL LIMIT 20; 
**LOGICAL OPERATIONS ON WHERE CLAUSE QUERIES:**  

                    SELECT name,year,rankscore FROM movies WHERE year>=1999 AND year<=2000; // AND 
                    SELECT name,year,rankscore FROM movies WHERE NOT year<=2000;  // NOT
                    SELECT name,year FROM movies WHERE rankscore>9 OR year>=2000;  // OR 
                    SELECT name,year,rankscore FROM movies WHERE year BETWEEN year>=1999 AND year<=2000; // BETWEEN 
                    SELECT director_id,genre FROM directors_genres WHERE genre IN('Comedy','Horror'); // IN 
                    SELECT name,year,rankscore FROM movies WHERE name LIKE 'Tis%'; // like , %-Wildcard character  
 **AGGREGATE FUNCTIONS:**  aggregate function is a function that performs a calculation on a set of values and returns a single summary value.

                    SELECT year, COUNT(year) FROM movies; 
                    SELECT year, COUNT(year) FROM movies WHERE year>=2000; 
                    SELECT year, MIN(year) FROM movies; 
                    SELECT year, MAX(year) FROM movies; 


 **GROUP BY:**  the GROUP BY clause is used to group rows that have the same values in specified columns into summary rows, like aggregating data. It is often used with aggregate functions (SUM(), COUNT(), AVG(), MIN(), MAX()) to perform operations on each group of rows.

                   SELECT year, COUNT(year) FROM movies GROUP BY year; 
                   SELECT year, COUNT(year) FROM movies GROUP BY year ORDER BY year; 
                   SELECT YEAR, COUNT(year) year_count FROM movies GROUP BY year ORDER BY year_count; 

**HAVING CLAUSE:** The HAVING clause in SQL is used to filter the results of a GROUP BY operation based on aggregate functions. Unlike the WHERE clause, which filters rows before any grouping takes place, the HAVING clause filters groups after the aggregation has been performed.

                  SELECT year, COUNT(year) year_count FROM movies GROUP BY year HAVING year_count>1000; 
                  SELECT year, COUNT(year) year_count FROM movies WHERE rankscore>9 GROUP BY year HAVING year_count>1000; 

**JOINS:** In SQL, joins are used to combine rows from two or more tables based on a related column between them. Joins allow you to retrieve data that is spread across multiple tables in a relational database. 

                 SELECT m.name, g.genre FROM movies m JOIN movies_genres g ON m.id=g.movie_id LIMIT 20; 
                 
