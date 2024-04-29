# GoogleCourseProject

This article dives into a case study for Cyclistic, a fictional Chicago bike-sharing company, focusing on how its marketing team can solve a business problem through data analysis. I'll be using Rstudio and Tableau to process and analyze the data, following a well-established 6-step process: Ask, Prepare, Process, Analyze, Share, and Act.

## 1. Ask
The first step is to clearly define the problems we aim to solve and understand the stakeholders' expectations. To achieve this, we'll delve into three key questions posed by Cyclistic's marketing director.
1. How do annual members and casual riders use bicycles differently?
2. Why do casual riders buy an annual membership in Cyclistic?
3. How does the Cyclistic use digital media to influence Casual riders to become members?

## 2. Prepare
Our analysis will leverage Cyclistic's historical trip data for the full year 2021 (January - December). To begin, we'll download all twelve CSV files containing this data and store them on our computer.

## 3. Process
Tackling 5 million data points can be a challenging task. To ensure efficient and fast analysis, I opted for RStudio over spreadsheets. Before diving in, we'll need to install essential R packages: tidyverse, janitor, skimr, and dplyr. These packages will streamline data manipulation tasks. Once installed, we can import all the CSV files for further processing.

Here are the steps I followed for data cleaning:
1. I made sure all column names were unique and consistent using clean_names(). This also ensured they only contained letters, numbers, or underscores.
2. I got rid of any empty columns or rows with remove_empty().
3. I removed duplicate entries by using distinct().
4. I deleted unnecessary columns (ride_id, end_station_id, start_lat, start_lng, end_lng, and end_lat).
5. I added new columns for analysis, like trip duration (in minutes), day of the trip, month of the trip, season of the trip, and start hour of the trip. 

After cleaning, I checked for any unusual data or errors, because there may still be some unsuitable data or errors.

I checked the minimum and maximum values for trip duration. I grouped it by the member type and also dropped the NA value. The View() function will help us to check the result in a new tab, so we can see it easily. Here is the result.

||Member Type|Max Trip Duration|Min Trip Duration|
|---|---|---|---|
|1|Casual|55944.150|-55.90000|
|2|Member|1495.633|-54.08333|

Our examination of trip duration revealed some illogical negative values. To address this, we filtered out trips with durations less than zero and removed rows containing missing data (NA values). This cleaning process resulted in a new, refined data frame. Before cleaning, the data contained 5,595,063 rows. Following the cleaning steps, we have a more concise dataset of 4,588,104 rows, ready for further analysis.

## 4. Analyze
Now that we've completed the cleaning process, we have suitable data and are prepared to analyze it. Let's revisit the initial question regarding the disparity in bicycle usage between annual members and casual members. I intend to visually represent this issue through observations using plots.

### - Member Type Distribution
![Rplot](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/3b20d4c4-00cc-4420-8077-29e062961e7e)

Our analysis reveals that casual riders make up about 44% of the total user base. This suggests a significant opportunity to convert existing casual riders into annual members, potentially offering a higher return on investment compared to acquiring entirely new customers. Let's explore how casual riders and annual members differ in their bicycle usage patterns.

### - Daily ride numbers
![Rplot2](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/cfa551c9-ca01-47e1-b98e-d5633dd6b1da)

### - Hourly ride numbers
![Rplot01](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/ef50545a-9357-4986-9c92-952fb3a2ba5d)

### - Monthly ride numbers
![Rplot02](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/a766a1ed-87e2-45b1-b3ff-52cb26895c25)

### - Seasonal ride numbers
![Rplot03](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/0e5382ea-502a-44f4-9f5e-ad8c347f9411)

### - Most popular station to start

From several statistics above we can conclude that:
1. 


1. Most popular station in general
2. Most popular station for casual member
3. Most popular station for annual member



## 5. Share
To reinforce the insights gleaned from our data cleaning process in R, I've created complementary visualizations using Tableau.  These visualizations will bring the data to life and provide a clear picture of the findings.  Head over to my dashboard to explore the interactive results!

## 6. Act
The final step in this analysis phase tackles the critical question: How can we leverage these findings to develop an effective marketing strategy?  Based on the insights we've uncovered throughout this process, I'd like to propose the following suggestions:

1. 
