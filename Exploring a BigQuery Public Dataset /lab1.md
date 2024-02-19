# Exploring a BigQuery Public Dataset

## Overview 
BigQuery is Google's enterprise data warehouse solution, offering super-fast SQL queries on massive datasets using Google's infrastructure. Accessible through the Cloud Console, CLI, or REST API, BigQuery simplifies data storage and querying. It enables tasks like querying public datasets, creating custom tables, loading data, and executing queries. With its user-friendly web UI, BigQuery streamlines data management and analysis, making it a valuable tool for businesses seeking efficient data handling solutions.

## Objectives
- Query a public dataset
-	Create a custom table
-	Load data into a table
-	Query a table

```sql
SELECT
  name, gender,
  SUM(number) AS total
FROM
  `bigquery-public-data.usa_names.usa_1910_2013`
GROUP BY
  name, gender
ORDER BY
  total DESC
LIMIT
  10

```
  
