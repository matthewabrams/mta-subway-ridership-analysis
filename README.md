# MTA Ridership Analysis Using SQL
Project Overview

This project analyzes MTA ridership data using SQL and SQLite to identify ridership trends, changes over time, and key patterns in the dataset.

The goal of this project is to demonstrate how SQL can be used to transform data, perform calculations, and answer business questions through data analysis.

# Business Questions

This analysis answers the following questions:

1) Which stations had the highest ridership?
2) Which borough had the highest overall ridership?
3) What was the largest year-over-year increase/decrease?
4) How far did ridership fall relative to 2019?
5) How has ridership recovered?
6) Which stations ranked highest within each borough?

# Dataset

The dataset contains monthly MTA ridership data.

Key Columns
Column	Description
Month	Month and year of the observation
Ridership	Total ridership recorded for the month

The Month field was transformed using SQL string functions to extract the year and organize the data chronologically.

# Tools & Technologies
SQL
SQLite
DB Browser for SQLite

# This project demonstrates the use of:
SELECT
WHERE
GROUP BY
ORDER BY
LIMIT
SUM()
AVG()
MIN()
MAX()
SUBSTR()
Common Table Expressions (CTEs)
Subqueries
Year-over-year calculations
Data transformation
Time-based analysis
Key Findings

# The analysis identified several trends in MTA ridership:

Ridership varied significantly across months.
Certain months consistently ranked among the highest and lowest ridership periods.
Year-over-year calculations highlighted significant changes in ridership between years.
Time-based transformations were necessary to accurately organize and compare ridership data.

Note: Specific findings and values are based on the results generated from the SQL queries included in this repository.

# Skills Demonstrated
SQL data analysis
Data cleaning and transformation
Time-series analysis
Aggregation and ranking
Year-over-year analysis
Business question development
SQLite
Data validation
Analytical problem solving
