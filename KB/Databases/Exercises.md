## 1. [[Find duplicate records]]
This is a common data validation query. Data that arrives via streaming, very often guarantee 'at least once' consistency but not 'exactly once'. 

## 2. Remove duplicate records

## 3. Find previous row (or delta)
For data such as meter reads or stock price, we sometimes want to show the difference from the last read or the percentage rate of change

## 4. Explode ranges into rows
Storing data as ranges is more compact but not always easy to work with as with a detailed row representation. It is helpful to be able to switch between those two representations

## 5. Group rows into ranges
Find contiguous ranges and group them together

## 6. Generate Data
Generating a sequence of integers or dates is a common task in reporting. Generating millions of rows is common in testing. Those can be of any data type and include randomization or a distribution 

## 7. Find missing rows or dates
While performing quality checks on data with ranges or detailed values, it is often important to know if the data has no 'holes' or missing values

## 8. Find overlapping ranges or intervals
While performing quality checks on data with ranges, it is often important to know if the data has overlapping ranges

## 9. Recursive query on a tree
A common table design practice is to have a child record point to a different parent record in the same table using its primary key. It is sometimes required to query the root of a record (regardless of depth) or list all the children or leaves of a node

## 10. Using windowed functions: row number, rank, percentile
When you are looking for the top n, rank, top n within a group, top n percent, n tile etc.

## 11. Find store with highest sales per product
This is a variation on rank. Use the sales row with the highest rank (top sales) to join with stores and get the store name

## 12. Split aggregate by another field (count 'yes' and 'no')
In case when within a group there are multiple variations and we want count (or sum) them in separate columns. This is good for fields that can be categorized into a known finite number of categories: yes/no, case closed within 2 days, 3-5 days, over 5 days etc.

## 13. Find top 3 stores by sales by region
A variation on rank. Filter results to only get the top 3 rows per group

## 14. Query based on a regular expression
It is now possible use a regular expression to process a character field, both for comparison and for substring extraction

## 15. Query a values inside a JSON
An alternative to storing JSON in cloud storage based data lake is to store it in a database field and later extract the required fields out of it. This is an example of parsing a field out of a JSON string

## 16. Query an array inside a JSON
Sometimes a JSON contains an array. In that case we can either extract an element by its position or explode the array into results rows, one for each element in the array

## 17. Parsing a CSV into a table
Another tactic for storing multiple values in a single database field is to use a CSV. Later, we may want parse the CSV into a table with separate rows

## 18. Constructing a CSV from a group by
This the opposite of 17. We want turn a set of grouped rows into a CSV

## 19. Constructing a CSV from an ARRAY
Here we want to convert an array into a CSV

## 20. Computing a running average or cumulative sum
This is a common way of smoothing values in a large data set before we display it on a chart

## 21. Compare two tables
This is a common task during testing of a transformation or data a migration. We are looking for any differences between the two tables: rows that exist in one table but not the other, rows that were modified in one table but not the other. We may or may not know the primary key of the table

## 22. Working with very large tables
When we do any type of work with a very large table, it is useful to do the development and initial testing on a smaller data set. There are a few techniques to support that

## 23. Performing statistical analysis
A very common task when looking at a large table at a client is to try to get a feel for the values in a column by looking a the values distribution, occurrences of NULLs, and outliers. There are tools that specialize in it and it is helpful to use a visualization tool such as tableau or Jupiter lab. But there is a lot you can do in straight SQL

## 24. Exploratory analysis on a table
In BigQuery it is possible to pass the query results directly into  Gsheet, CoLab, or Looker for visualization or further analysis

## 25. Working in local time (and daylight saving)
Working in local time with daylight saving is always tricky. Datetime data should be stored in Unix time, as a timestamp in UT (GMT), or as a timestamp with an offset. There are built in functions to convert among the different representations

## 26. Working with Geospatial data
Support for geospatial data is a relatively recent addition to decision support databases. You can now add points, lines and polygons and query about how they are organized relative to each other 

## 27. Working with Unicode strings
Some languages use multibyte characters. What are the things we need to keep in mind while working with non English text?

## 28. Group by top n and 'other' category
For ease of visualization, it is sometimes helpful to show in addition to the top n values, another value  called 'other' where all the smaller values are represented. This can be done by the query itself

## 29. [[Working with INFORMATION_SCHEMA]]
Information schema is a standard schema that stores meta-data about the structure of the database, such as the tables, columns, constraints etc. 

## 30. Show commonly used queries
What queries are repeating the most

## 31. [[Show expensive queries]]
What queries take the longest to run? Cost the most?

## 32. Show Heavy users
Who are the users that cost the most to the organization? Who are the ones that run the most queries?

## 33. [[Show Largest tables]]
What are the largest 10 tables in a database by number of rows and by space used?

## 34. Improving query performance
What can we do to improve the performance of a slow running query? Can we see the execution graph?

## 35. Time travel without updating rows
Create and query a Type 2 SCD without updating the previous row's expired_at. I.e. when a value changes a new rows gets added for it with only a created_at









