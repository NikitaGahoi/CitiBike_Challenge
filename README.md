# CitiBike_Challenge

## Overview

This project involves the cleaning and analysis of New York Citibike trip data. The Python script (`data_cleaning_analysis.py`) combines multiple CSV files, performs data cleaning, calculates trip durations, identifies outliers, and creates a cleaned dataset for further analysis. The data is sourced from the Citibike bike-sharing program in New York City.

## File Description

- **[data_cleaning_analysis.py:](https://github.com/NikitaGahoi/CitiBike_Challenge/blob/main/CitiBike_data_preprocessing.ipynb)** Python script for data cleaning and analysis.
- **[Tableau Analysis:](https://public.tableau.com/views/Citibike_2_16989636340030/DayHourAnalysis?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link)** Cleaned data file was uploaded into Tableau for a detailed analysis of New York's CitiBike data. This file can be accessed by clicking at the [link](https://public.tableau.com/views/Citibike_2_16989636340030/DayHourAnalysis?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link)

## Data Preprocessing steps:

1. **Install Dependencies:**
- Ensure that you have the necessary dependencies installed
2.  **Combining Data:**
- Concatenating CSV files from Jan 2023(Winter), April 2023(Spring) and July 23 (Summer) (`202301.csv`, `202304.csv`, `202307.csv`) from New York Citibike database into one dataframe.
3. **Data Cleaning:**
- Columns 'started_at' and 'ended_at' are converted to datetime format.
- Trip durations are calculated in minutes and days.
- Rows with time differences less than or equal to 60 seconds are removed, as they might just be a false trip (as stated at the New York Citibike database)
- Unnecessary columns are dropped
4. **Outlier Identification:**
- Quartiles and inter-quartile range (IQR) are calculated.
- Outliers are identified based on the calculated bounds.
5. **Additional Analysis:**
- Month and season columns are created for further analysis.
6. **Save Cleaned Dataset:**
- The cleaned dataframe is saved to a CSV file (`clean_citibike_2023_jan-apr-jul(2).csv`). This cleaned dataset was then used for analysis in Tableau

## Tableau Analysis
The cleaned dataframe is saved to a CSV file (`clean_citibike_2023_jan-apr-jul(2).csv`) was imported into tableau, and a few calculations were performed:
-  **Time_Duration in minutes** was calculated by substracting the end time with the start time of the trip
-  **Distance in Miles** was calculated by first calculting the origin and destination points using `MAKEPOINT` function in Tableau and then Distance between origin and destination points was claculated using the `DISTANCE` function in Tableau.
-  After performing these calculations, the graphs were created to understand various statistics about the new york CitiBike usage. all the graphs were then arranged into the dashboard to get a comprehensive understanding of the analysis

### User Analysis  

CitiBike users fall into two categories: **Members**, who have an annual subscription, and **Casual riders**, who use the service intermittently. The dashboard presents statistics specific to each user type. The following conclusions arise from this analysis:
-  Members constitute the majority of CitiBike users, accounting for approximately 80.45% of all rides, while casual riders contribute to the remaining 19.44%.
-  Despite notable differences in the average trip duration between members and casual riders, both groups cover an equal average distance of one mile per ride.
-  Number of bike trips in Summer is the highest followed by spring and winter

![image](https://github.com/NikitaGahoi/CitiBike_Challenge/assets/136101293/3bc59db6-dbea-4ac0-b464-77b23f65ddf4)

### Peak Hours and Weekday Analysis 

This analysis was conducted to gain insights into the utilization patterns of CitiBikes, specifically focusing on variations across hours, weekdays, and member types. The following conclusions emerge from this in-depth examination:
-  Weekdays see peak CitiBike usage at 8 am and 5 pm, primarily by members. The average trip duration at these hours is approximately 11.5 minutes. This pattern holds throughout the week, indicating members rely on CitiBike for their daily office commute.
-  Members favor weekdays, while weekends are preferred by casual riders. This underscores the recurring observation that members predominantly rely on CitiBike for their daily work commute.
-  Members favor commuting at 8 am and 5 pm, aligning with standard work hours, while casual riders prefer the timeframe from noon to 7 pm,  indicating a more flexible usage pattern during the later part of the day.
-  **Saturday** is the most popular day for the bike ride, for both memebers as well as casual users

![image](https://github.com/NikitaGahoi/CitiBike_Challenge/assets/136101293/a1e34b97-f3bb-4cc0-b356-7b87b1bdacc2)

### CitiBike Station Analysis

New York CitiBike recorded a substantial 8.1 million bike trips within a three-month period (Jan 2023, Apr 2023, and Jul 2023), encompassing a network of 1,962 start stations and 1,980 end stations. This analysis aims to identify the most popular start and end stations and gain insights into their geographical distribution in New York. The following conclusions can be drawn from this comprehensive analysis:
-  **W 21 St. and 6 Ave** is the most popular Start and End Stations followed by **Broadway & W 58 St**
-  Top 10 start station and End Station ar e apart of Midtown and Lower Manhattan Neighbourhood

![image](https://github.com/NikitaGahoi/CitiBike_Challenge/assets/136101293/6cc08247-4750-43cf-be67-839e3f972a93)

### Geographical Location of the Start and End Stations
All the start and end stations were mapped, to visualize the map locations and their popularity.

![image](https://github.com/NikitaGahoi/CitiBike_Challenge/assets/136101293/db96b79e-86e6-4828-a873-d7b4016719e2)













