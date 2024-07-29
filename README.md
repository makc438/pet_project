# Case Study Cyclistic Bike Share


## Introduction
This project is part of the Google Data Analytics course and focuses on analyzing data from the Cyclistic Bike Share company. We explored bike usage data, created SQL queries for data processing, and visualized the data in Power BI. In order to answer the business questions, i follow the steps of the data analysis process: Ask, Prepare, Process, Analyze, Share, and Act.

## About Cyclistic Company
Cyclistic is a Bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, your team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, your team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve recommendations, so they must be backed up with compelling data insights and professional data visualizations.

Cyclistic: A bike-share program that features more than 5,800 bicycles and 600 docking stations. Cyclistic sets itself apart by also offering reclining bikes, hand tricycles, and cargo bikes, making bike-share more inclusive to people with disabilities and riders who can’t use a standard two-wheeled bike. The majority of riders opt for traditional bikes; about 8% of riders use the assistive options. Cyclistic users are more likely to ride for leisure, but about 30% use the bikes to commute to work each day.
In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime.
One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships.
Customers who purchase single-ride or full-day passes are referred to as casual riders.
Customers who purchase annual memberships are Cyclistic members.

Cyclistic’s finance analysts have concluded that annual members are much more profitable than casual riders. Rather than creating a marketing campaign that targets all-new customers, there is a solid opportunity to convert casual riders into members.

### Ask
Three questions will guide the future marketing program:
1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

But i need to answer on the first question:
"How do annual members and casual riders use Cyclistic bikes differently?"

## Prepare
### Data
[Data Source](https://divvy-tripdata.s3.amazonaws.com/index.html) I used data from 202301-divvy-tripdata to 202312-divvy-tripdata
Data Range January 2023 - December 2023
I used SQL Server Management Studio to Prepare, Process and Analyze data.

**The dataset contains the following columns:** <br>
- ride_id: Unique identifier for each ride
- rideable_type: Type of bike used
- started_at: Start date and time of the ride
- ended_at: End date and time of the ride
- start_station_name: Name of the start station
- end_station_name: Name of the end station
- member_casual: Type of user (member or casual)


[Data Combine](https://github.com/makc438/pet_project/blob/main/Combine_Data)
After loading the data, I combined it into a single SQL file.
Then I deleted the following rows:
start_station_id, end_station_id, start_lat, start_lng, end_lat and end_lng.
Because they didn't help me analyze the data.

## Process
[Process Phase](https://github.com/makc438/pet_project/blob/main/Process%20Phase)
### Data Cleaning
### Identify and Remove Null Values
First, I identified rows with null values in crucial columns and then removed these rows.
Before this query, the dataset contained 5,719,877 rows. After removing 1,387,808 rows with null values, the dataset was reduced to 4,332,069 rows.

### Identify and Remove Duplicate Values
Next, I checked for duplicate rows in the dataset based on crucial columns. The query returned no duplicate values, confirming the data's uniqueness.

## Analyze
**Objective:** Analyze how annual members and casual riders use Cyclistic bikes differently.
Tools Used: <br>
SQL Server Management Studio - Used for writing queries
Power BI - Used for data visualization

### Rides by member and casual users
Comparison of the total number of rides taken by annual members versus casual riders.
[total_rider](https://github.com/makc438/pet_project/issues/1#issue-2436223816)
**Key Insights:** <br>
- Ride Frequency Comparison: Annual members have taken significantly more rides (2,800,128 or 64,64%) compared to casual riders (1,531,941 or 35,36%). This indicates that annual members are more frequent users of the bike share system than casual riders.

### Total Rides by Bike Type and User Type
Analysis of how different types of bikes are used by annual participants and regular riders.
