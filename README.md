# SQL-OPERATIONS-ON-IMDB-DATASET 
Performed SQL operation on the IMDB dataset for practicing SQL query operations and building database-driven applications. It represents a structured collection of data about movies, actors, directors, ratings, and other related information.

**1. SELECT QUERY:** A SELECT query in SQL is a command used to retrieve data from one or more tables in a database. 

                    SELECT * FROM movies; '*' defines that set of all rows with column names. 
                    SELECT name,rankscore FROM movies; 
                       
**2.LIMIT:** The LIMIT clause in SQL is used to specify the maximum number of rows to be returned in the result set of a query. 

                    SELECT name.year FROM movies LIMIT 20;
                     
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
