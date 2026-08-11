# NYC MTA Ridership Analysis Using SQL and Power BI


<img width="1515" height="810" alt="Screenshot 2026-08-11 172456" src="https://github.com/user-attachments/assets/0a225b87-4859-4962-99e1-8382b4f8268c" />


# Project Overview

This project analyzes MTA ridership data using SQL and SQLite to identify ridership trends, changes over time, and key patterns in the dataset.

The goal of this project is to demonstrate how SQL can be used to transform data, perform calculations, and answer business questions through data analysis.

# Business Questions

This analysis answers the following questions:

1) Which stations had the highest ridership?
2) Which borough had the highest overall ridership?
3) What was the largest year-over-year increase/decrease?
4) How far did ridership fall relative to 2019?
5) How has ridership recovered?
6) Which stations are ranked high?

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
10) RANK()
11) CAST()
12) SUBSTR()
13) REPLACE()
14) Common Table Expressions (CTEs)
15) Year-over-year calculations
17) Time-based analysis
18) Key Findings

# The analysis identified several trends in MTA ridership:

1) 2020 ridership declined 62.19% YoY.
2) Ridership recovered to 76.6% of the 2019 baseline by 2025.
3) Manhattan had the highest cumulative ridership.
4) Recovery accelerated through 2022 before slowing in subsequent years.
5) 2026 is analyzed separately on a YTD basis due to incomplete data.

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

# Favorite Queries (Most Insightful and can be seen in Screenshots)

Query #1 — Busiest Subway Stations Results 

The data indicates that ridership is highly concentrated around major Manhattan transportation hubs. These locations connect multiple subway lines and serve major employment, commercial, tourism, and transfer destinations.

Note: These are cumulative totals across the observations in your dataset, not necessarily ridership on a single day or month.

Query #2 - Ridership by Borough (Overall Total Rides and Monthly Average) Results 

Manhattan has by far the highest cumulative ridership, accounting for substantially more ridership than any other borough. Brooklyn is second, followed by Queens and the Bronx. The Staten Island value of 5 is clearly an anomaly relative to the rest of the dataset. The dataset contains extremely low Staten Island ridership values, suggesting incomplete, missing, or otherwise anomalous source data for that borough. Queens has a higher average than Brooklyn, despite Brooklyn having substantially higher total ridership.

Query #4 — Year-over-year Ridership Change Results 

The major story is clearly COVID-19's impact.

Ridership was growing modestly before COVID.
* 2020 experienced a massive 62.19% decline.
* Recovery began in 2021 (+18.75%).
* 2022 was the strongest recovery year at +33.58%.
* Growth continued in 2023 (+13.93%).
* Growth slowed considerably in 2024 (+4.14%).
* 2025 accelerated somewhat to +7.70%.

Note: 2026 figure is not comparable to a completed year as the dataset only contains part of 2026.

Query #7 — COVID impact compared with 2019 

2019 provides a useful pre-COVID baseline.

By 2020, the system fell to only 37.81% of 2019 ridership.

Then recovery was gradual:

1) 2020 → 37.8%
2) 2021 → 44.9%
3) 2022 → 60.0%
4) 2023 → 68.3%
5) 2024 → 71.2%
6) 2025 → 76.6%

So even though ridership has recovered substantially, 2025 was still about 23.36% below 2019.

Query #9 — Transfer activity relative to ridership Results

This answers which stations have the highest transfer activity relative to their ridership. Note a condition was made where total ridership exceeds 1,000 rides. Without it, this would make the station at Staten Island having the highest transfer activity despite the data showing 5 rides total. 

The Tompkinsville (SIR) result immediately stands out:
1 transfer / 4 ridership = 25%

Without it, top results include:

Station	               -                     Borough	  -   Transfer Rate
1) Bay Pkwy (F)	            -                  Brooklyn	   -   31.88%
2) Jamaica-179 St (F)	          -              Queens	   -     29.25%
3) Jamaica Center-Parsons/Archer (E,J,Z)	 -     Queens	 -       27.96%
4) Kew Gardens-Union Tpke (E,F)	        -      Queens	   -     27.89%
5) Pelham Bay Park (6)	          -              Bronx	 -         26.89%
6) Woodlawn (4)	               -               Bronx	    -      26.64%
7) Flushing-Main St (7)	          -            Queens	    -    24.74%
8) 86 St (R)	                   -               Brooklyn	   -   21.07%
9) Middle Village-Metropolitan Av (M)	   -     Queens	     -   20.45%
10) Van Cortlandt Park-242 St (1).       -     Bronx.      -   20.07%

Manhattan stations are not in the top 10 for transfer activity rates despite having more rides over other boroughs.


# DAX

A) Total Ridership = SUM('MTA_Subway_Station_Monthly_Ridership__Beginning_February_2017_20260809 (2)'[ridership])

What it does:
1) It adds together all values in the ridership column from the MTA dataset that are included in the current filter context.

B) 2019 Ridership = calculate([Total Ridership],REMOVEFILTERS(DateTable),DateTable[Year]=2019)

What it does:
1) [Total Ridership] → your existing ridership measure.
2) REMOVEFILTERS(DateTable) → removes the current year/date filters.
3) DateTable[Year] = 2019 → then forces the calculation to use 2019.

C) Recover Vs 2019 = DIVIDE([TOTAL RIDERSHIP], [2019 RIDERSHIP])

What it does:
1) It compares the currently selected year's ridership against the fixed 2019 baseline.
2) So 80% doesn't mean ridership increased 80%. It means ridership reached 80% of the 2019 level.
3) 2019 point should be 100%, and subsequent years show how close ridership came to the 2019 baseline.
