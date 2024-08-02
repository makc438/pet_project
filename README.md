# Case Study Cyclistic Bike Share


## Introduction
This project is part of the Google Data Analytics course and focuses on analyzing data from the Cyclistic Bike Share company. I explored bike usage data, created SQL queries for data processing, and visualized the data in Power BI. In order to answer the business questions, i follow the steps of the data analysis process: Ask, Prepare, Process, Analyze, Share, and Act.

## About Cyclistic Company
Cyclistic is a Bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships. Therefore, my team wants to understand how casual riders and annual members use Cyclistic bikes differently. From these insights, my team will design a new marketing strategy to convert casual riders into annual members. But first, Cyclistic executives must approve recommendations, so they must be backed up with compelling data insights and professional data visualizations.

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

### Prepare
#### Data
[Data Source](https://divvy-tripdata.s3.amazonaws.com/index.html) I used data from 202301-divvy-tripdata to 202312-divvy-tripdata.
**Data Range:** January 2023 - December 2023
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

### Process
[Process Phase](https://github.com/makc438/pet_project/blob/main/Process%20Phase)
#### Data Cleaning
#### Identify and Remove Null Values
First, I identified rows with null values in crucial columns and then removed these rows.
Before this query, the dataset contained 5,719,877 rows. After removing 1,387,808 rows with null values, the dataset was reduced to 4,332,069 rows.

#### Identify and Remove Duplicate Values
Next, I checked for duplicate rows in the dataset based on crucial columns. The query returned no duplicate values, confirming the data's uniqueness.

### Analyze
**Objective:** Analyze how annual members and casual riders use Cyclistic bikes differently.
Tools Used: <br>
- SQL Server Management Studio - Used for writing queries.
- Power BI - Used for data visualization.

#### Rides by member and casual users
Comparison of the total number of rides taken by annual members versus casual riders.
![total_rider](https://github.com/user-attachments/assets/6d7fa917-2260-42bc-8d63-44c86b4f47c4)
**Key Insights:** <br>
- **Ride Frequency Comparison:** Annual members have taken significantly more rides (2,800,128 or 64,64%) compared to casual riders (1,531,941 or 35,36%). This indicates that annual members are more frequent users of the bike share system than casual riders.

#### Total Rides by Bike Type and User Type
Analysis of how different types of bikes are used by annual participants and regular riders.
![Total Type](https://github.com/user-attachments/assets/25f1760a-9fe6-47cc-a857-2a927f387e15)
**Key Insights:** <br>
**Bike Type Preferences:** <br>
- Classic Bikes are the most popular among both annual members (1,817,826 rides) and casual riders (873,063 rides).
- Electric Bikes are also favored by annual members (982,302 rides), though less so by casual riders (582,638 rides).
- Docked Bikes are primarily used by casual riders (76,240 rides) with minimal use by annual members.

This suggests that while annual members prefer classic and electric bikes significantly more than casual riders, casual riders have a notable preference for docked bikes.

#### Average ride lenght
Сompare the average ride length between annual members and casual riders.
![Average ride lenght](https://github.com/user-attachments/assets/0af40448-5a99-48e7-9661-22e1d1dfe011)
**Results:** <br>
- Annual Members: 12.13 minutes
- Casual Riders: 22.94 minutes

**Key Insights:** <br>
**Ride Duration Comparison:** <br>
- Annual Members have a significantly shorter average ride length of 12.13 minutes compared to Casual Riders, who average 22.94 minutes. This indicates that casual riders typically use the bike share system for longer durations per ride compared to annual members.

#### Mostly used start station by member and casual users
Identify and compare the top start stations used by annual members versus casual riders.
![Mostly used start station](https://github.com/user-attachments/assets/1e6ad5e4-f156-4261-87a2-0fe9acfe1426)
**Key Insights:** <br>
- **Popular Start Stations:** Casual riders frequently use stations like Streeter Dr & Grand Ave and DuSable Lake Shore Dr & Monroe St, while annual members favor stations such as Clinton St & Washington Blvd and Kingsbury St & Kinzie St.
- **Usage Patterns:** The data shows that certain stations are notably more popular among one user type compared to the other, reflecting different usage patterns and preferences.

#### Monthly Trip Distribution by User Type
Distribution of trip counts by month for annual members and casual riders, identifying seasonal trends.
![Monthly Trip](https://github.com/user-attachments/assets/06546953-35ec-4840-9f64-9acd6b91af19)
**Key Insights:** <br>
**Seasonal Trends:** <br>
- **Annual Members:** Peak usage in the summer months (June, July, August), with the highest number of trips in August (351,063). Usage declines during the colder months, but members still maintain a higher baseline of trips compared to casual riders.
- **Casual Riders:** Also exhibit peak usage in the summer months, with the highest number of trips in July (245,359). However, their usage drops more sharply during the colder months compared to annual members.

#### Monthly Average Ride Length by User Type
Average ride length per month for annual members and casual riders.
![monthlength](https://github.com/user-attachments/assets/4765f464-135e-4ddf-a9a9-6b47098efccd)
**Key Insights:** <br>
**Monthly Ride Length Patterns:** <br>
- **Casual Riders:** The average ride length for casual riders tends to be longer than that of annual members across all months. The peak average ride length occurs in July (25.22 minutes), followed by May (24.52 minutes) and June (24.07 minutes).
- **Annual Members:** The average ride length for annual members is relatively consistent, with a slight increase during the summer months. The peak average ride length occurs in July (13.35 minutes) and August (13.31 minutes).

#### Weekly Trip Distribution by User Type
The distribution of trip counts by day of the week for annual members and casual riders.
![Weekly Trip](https://github.com/user-attachments/assets/d2878b7c-2c9e-4cf5-b53d-94f5d490d449)
**Key Insights:** <br>
**Daily Usage Patterns:** <br>
- **Annual Members:** The highest number of trips occur mid-week, with peak usage on Wednesday (452,744 trips) and Thursday (452,690 trips). The number of trips decreases towards the weekend, with the lowest on Sunday (307,890 trips).
- **Casual Riders:** The highest number of trips occur on weekends, with peak usage on Saturday (310,195 trips) and Sunday (254,796 trips). The number of trips is lower during the weekdays, with Monday (175,433 trips) being the least busy day.

#### Average Ride Length by Day of the Week and User Type
Average ride length for each day of the week for annual members and casual riders.
![weeklength](https://github.com/user-attachments/assets/8a7945a1-7c37-457a-a10a-1487a94b23be)
**Key Insights:** <br>
**Daily Ride Length Patterns:** <br>
- **Casual Riders:** The average ride length for casual riders tends to be longer than that of annual members across all days. The peak average ride length occurs on Sunday (26.56 minutes) and Saturday (25.92 minutes).
- **Annual Members:** The average ride length for annual members is relatively consistent, with slightly longer rides on weekends. The peak average ride length occurs on Sunday (13.61 minutes) and Saturday (13.58 minutes).

### Hourly Trip Distribution by User Type
Distribution of trip counts by hour of the day for annual members and casual riders.
![image](https://github.com/user-attachments/assets/ec21fb22-378f-49ea-ab86-af1af42c7f42)
**Key Insights:** <br>
**Hourly Usage Patterns:** <br>
- **Annual Members:** The highest number of trips occur during evening rush hours, particularly at 17:00 (5 PM) with 303,528 trips, followed by 16:00 (4 PM) with 258,648 trips. There is also significant usage in the morning at 08:00 (8 AM) with 194,782 trips, indicating a strong pattern of commuting.
- **Casual Riders:** The highest number of trips also occur at 17:00 (5 PM) with 150,656 trips, followed by 16:00 (4 PM) with 138,646 trips. However, casual riders have a more evenly distributed pattern throughout the day, with notable peaks during the afternoon hours.

### Share
Visualization Power Bi in Google Drive - [File](https://drive.google.com/file/d/1f4G633sg1UsiSCyDIdMbbvbpV-IvnpMM/view?usp=drive_link)

**Key Findings:** <br>
- **Ride Frequency:** <br>
Annual members took 2,800,128 rides, while casual riders took 1,531,941 rides.
- **Rideable Types:** <br>
Annual members primarily used classic bikes (1,817,826 rides) and electric bikes (982,302 rides), whereas casual riders also preferred classic bikes (873,063 rides) and electric bikes (582,638 rides).
- **Station Usage:** <br>
The most frequently used start and end stations for both user types were identified, with Streeter Dr & Grand Ave being the top station for casual riders.
- **Ride Length:** <br>
The average ride length for casual riders was 22.94 minutes, compared to 12.13 minutes for annual members.
- **Time of Use:** <br>
Peak usage times and days were analyzed, showing that members tend to ride during weekdays, while casual riders peak during weekends.

### Act
**Recommendations:** <br>

- **Increase Membership:** <br>
  Develop marketing campaigns targeting casual riders to convert them to annual members, focusing on the benefits of membership. Highlight the benefits of annual membership, such as cost savings and convenience.
- **Optimize Bike Distribution:** <br>
  Place more bikes at popular start and end stations identified for each user type to meet demand. Increase the number of bikes at top start and end stations during peak times.
- **Enhance User Experience:** <br>
  Improve the availability and maintenance of classic and electric bikes, particularly on weekends for casual riders. Implement a system to gather user feedback on bike conditions and station availability.
- **Seasonal Promotions:** <br>
  Offer seasonal promotions and incentives to boost ridership during less busy months.

