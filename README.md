# Surfs_Up
Python, SQL Lite

## Overview of Project
The purpose of this project was to query and filter by date a sqlite data file, load the query results to a pandas dataframe, and perform summary statistics on the results.


## Results
After querying the data and loading to a pandas dataframe, I was able to use the describe function to summarize statistics on the dataset.
June Statistics

![June Temp Statistics](/Images/JuneStats.PNG)


December Statistics

![Dec Temp Statistics](/Images/DecStats.PNG)

The biggest takeaways from the data regarding temperatures
* The temperature in Hawaii does not vary much month to month
* The quarterly percentile differences were the same 2-3 degrees for both summer and winter months
* The biggest fluctuation in temperatures was at the minimum temp variable

## Summary
Using a function to extract the columns from the sqlite table, I notice there is also precipitation data in the same Measurement table. 

![sqlite columns](/Images/Columns.PNG)

We could extract precipitation data from Measurement table and run desribe to get precipitation statistics for both months.
session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==6).all()

![June Precip Statistics](/Images/JunePrecip.PNG)

session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==12).all()

![Dec Precip Statistics](/Images/DecPrecip.PNG)
