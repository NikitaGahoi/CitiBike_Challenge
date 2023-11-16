# CitiBike_Challenge

## Overview

This project involves the cleaning and analysis of New York Citibike trip data. The Python script (`data_cleaning_analysis.py`) combines multiple CSV files, performs data cleaning, calculates trip durations, identifies outliers, and creates a cleaned dataset for further analysis. The data is sourced from the Citibike bike-sharing program in New York City.

## File Description

- **data_cleaning_analysis.py:** Python script for data cleaning and analysis.

## Data Preprocessing steps:

1. **Install Dependencies:**  Ensure that you have the necessary dependencies installed
2.  **Combining Data:**  Concatenating CSV files from Jan 2023(Winter), April 2023(Spring) and July 23 (Summer) (`202301.csv`, `202304.csv`, `202307.csv`) from New York Citibike database into one dataframe.
3. **Data Cleaning:**
- Columns 'started_at' and 'ended_at' are converted to datetime format.
- Trip durations are calculated in minutes and days.
- Rows with time differences less than or equal to 60 seconds are removed, as they might just be a false trip (as stated at the New York Citibike database)
- Unnecessary columns are dropped.
4. **Outlier Identification:**
- Quartiles and inter-quartile range (IQR) are calculated.
- Outliers are identified based on the calculated bounds.
4. **Additional Analysis:**
- Month and season columns are created for further analysis.
5. **Save Cleaned Dataset:**
- The cleaned dataframe is saved to a CSV file (`clean_citibike_2023_jan-apr-jul(2).csv`).


