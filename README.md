# MTA Ridership Analysis Using SQL 2017-2026
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

1) Key Columns
2) Column	Description
3) Month	Month and year of the observation
4) Ridership	Total ridership recorded for the month

The Month field was transformed using SQL string functions to extract the year and organize the data chronologically.

# Limitations

1) 2017 contains incomplete data because January is unavailable.
2) 2026 is incomplete and is therefore analyzed on a YTD basis.
3) Data referring to Staten Island is treated as an outlier given only 4 records (rows) totaling 5 rides within the timeframe is unusual.

# Tools & Technologies
1) SQL
2) SQLite
3) DB Browser for SQLite

# This project demonstrates the use of:
1) SELECT
2) WHERE
3) GROUP BY
4) ORDER BY
5) LIMIT
6) SUM()
7) AVG()
8) MIN()
9) MAX()
10) CAST()
11) REPLACE()
12) Common Table Expressions (CTEs)
13) Year-over-year calculations
14) Data transformation
15) Time-based analysis
16) Key Findings

# The analysis identified several trends in MTA ridership:

1) Ridership varied significantly across months.
2) Certain months consistently ranked among the highest and lowest ridership periods.
3) Year-over-year calculations highlighted significant changes in ridership between years.
4) Time-based transformations were necessary to accurately organize and compare ridership data.

Note: Specific findings and values are based on the results generated from the SQL queries included in this repository.

# Skills Demonstrated
1) SQL data analysis
2) Data cleaning and transformation
3) Time-series analysis
4) Aggregation and ranking
5) Year-over-year analysis
6) Business question development
7) SQLite
8) Data validation
9) Analytical problem solving
