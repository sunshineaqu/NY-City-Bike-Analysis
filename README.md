# New York Citi Bike Analytics

## Background

![Citi-Bikes](Images/citi-bike-station-bikes.jpg)

[New York Citi Bike](https://en.wikipedia.org/wiki/Citi_Bike) Program is the largest bike sharing program in the United States. Since 2013, the Citi Bike Program has implemented a robust infrastructure for collecting data on the program's utilization. Through the team's efforts, each month bike data is collected, organized, and made public on the [Citi Bike Data](https://www.citibikenyc.com/system-data) webpage.

However, while the data has been regularly updated, the team has yet to implement a dashboard or sophisticated reporting process. City officials have a number of questions on the program, so the task is to build a set of data reports to provide the answers and provide business insights for improving the city program. 

## Task

**Aggregate the data found in the Citi Bike Trip History Logs to build a data dashboard, story, or report.**

<p align="center">
  <a href="#data-source">Data Source and Preparation</a> •
  <a href="#findings">Findings</a> •
  <a href="#technology-Used">Technology Used</a>
</p>

## Data Source and Preparation

* Data Source
This [Citi Bike Data](https://www.citibikenyc.com/system-data) has been processed to remove trips that are taken by staff as they service and inspect the system and any trips that were below 60 seconds in length 
(potentially false starts or users trying to re-dock a bike to ensure it's secure). The analysis was performed using New York [Citi Bike Trip Histories Data](https://s3.amazonaws.com/tripdata/index.html) for year 2018 (monthly csv files 201801-citibike-tripdata.csv.zip to 201812-citibike-tripdata.csv.zip).

* Data Preaparation (Select Half)
The whole 2018 trip history dataset is a very large dataset with more than 15 million rows, which exceeds the up limit that Tableau can handle. We end up randomly cutting half the records for better performance.
1. Conbine the monthly csv files to one csv file using python in Jupyter notebook.
2. Clean the data: drop NA, remove age>90, reduce file size by keeping every other raw after sorting by trip start time.
3. Transform the birth year and trip duration data to age and trip duration in minutes.
4. Export it as a csv files for Tableau useage.

## Findings

By analyzing trip histories Data in New York city druing whole 2018, we found the followings: 

**User Analysis**
![user analysis](Images/user-analysis.png)
According to analyze half of 2018 trip records (8,766,192 records), we found most users are subscribers (89%), only 11% are Subscribers. Male are dominant users, accouting for 68% of all the trips. Females account for 23%. There are also 8% users did not release their gender information. In the future, promotions targeting female users may help increase the overall benefit. 

Accorss different ages, we found age 25-29 ride most, following by 30-34 year range. 

**Busiest Time Analysis** 
![time analysis](Images/time-analysis.png)
As expected, May to October have higher number of trips then the rest of the year, possibly due to the nice weather. Accorss different seasons, we found similar businest hour pattern, with 17pm the highest starting time and 8am the 2nd highest starting time. This may be related people were biking to and from work. We also noticed different trends between weekdays and weekend. 

**Bike Station Analysi** (popular locations?)
![location analysis](Images/location-analysis.png)
We found the top stations are around Pershing Square North. 

**Unexpected Phenomena** 
For the number of trips among different ages and gender, there is a supprisingly high usage among 45-49 year range. By looking into it, those are mainly from age 49 and unknown gender riders. 

## Limitations
We randomly picked half of the records from 2018 due to the up limit of Tableau (15 million rows). It would not impact the trend of the analysis. But there might be slight difference between this analysis and analysis of the whole data.







