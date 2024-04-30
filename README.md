# GoogleCourseProject

This article dives into a case study for Cyclistic, a fictional Chicago bike-sharing company, focusing on how its marketing team can solve a business problem through data analysis. I'll be using Rstudio to process and analyze the data, following a well-established 6-step process: Ask, Prepare, Process, Analyze, Share, and Act.

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

Weekend trends differ for casual and annual members. Casual riders ramp up their cycling activity on weekends, while members take fewer rides compared to weekdays.

### - Hourly ride numbers
![Rplot01](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/ef50545a-9357-4986-9c92-952fb3a2ba5d)

Members exhibit a distinct double-peak pattern throughout the day. Their trip frequency surges early in the morning (6-8 AM) and again in the evening (4-8 PM). In contrast, casual riders demonstrate a steady rise in trips throughout the day, peaking in the evening before tapering off.

### - Monthly ride numbers
![Rplot02](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/a766a1ed-87e2-45b1-b3ff-52cb26895c25)

### - Seasonal ride numbers
![Rplot03](https://github.com/tedylimanto/GoogleCourseProject/assets/141625821/0e5382ea-502a-44f4-9f5e-ad8c347f9411)

Interestingly, both casual and annual members demonstrate similar trip patterns throughout the year, with peak activity in fall and summer and a dip in winter. Notably, the ridership gap between these two groups is narrow during June, the peak summer month.

### - Most popular station to start

1. Most popular station in general

||Start Station Name|
|---|---|
|1|Streeter Dr & Grand Ave|
|2|Dusable Lake Shore Dr & Monroe St|
|3|Dusable Lake Shore Dr & Monroe Blvd|
|4|Michigan Ave & Oak St|
|5|Wells St & Concord Ln|
|6|Millenium Park|
|7|Clark St & Elm St|
|8|Kingsburry St & Kinzie St|
|9|Theater on the Lake|
|10|Wells St & Elm St|

2. Most popular station for casual member
   
||Start Station Name|
|---|---|
|1|Streeter Dr & Grand Ave|
|2|Dusable Lake Shore Dr & Monroe St|
|3|Millenium Park|
|4|Michigan Ave & Oak St|
|5|Dusable Lake Shore Dr & North Blvd|
|6|Shedd Aquarium|
|7|Theater on the Lake|
|8|Wells St & Concord Ln|
|9|Dusable Harbor|
|10|Clark St & Armitage Ave|

3. Most popular station for annual member

||Start Station Name|
|---|---|
|1|Kingsbury St & Kinzie St|
|2|Clark St & Elm St|
|3|Wells St & Concord Ln|
|4|Clinton St & Washington Blvd|
|5|Loomis St & Lexington St|
|6|Clinton St & Madison St|
|7|University Ave & 57th St|
|8|Ellis Ave & 60th St|
|9|Wells Street & Elm St|
|10|Streeter Dr & Grand Ave|

Summary:

|Casual|Member|
|---|---|
|Tends to use bikes throughout the day, more frequently over the weekends in summer and fall for leisure activities|Tends to use bikes on weekdays during commute hours (8 am/5 pm) in summer and fall|
|Travel 2 times longer but less frequently compared with member|Travel more frequently but with shorter ride duration (Approximately  half of the casual rider's trip duration|
|Start and end their journey around vocational locations such as parks, museums, along the coast, and other recreational sites|Start and end their journey around working areas such as universities, residential and commercial areas|

## 5. Act
The final step in this analysis phase tackles the critical question: How can we leverage these findings to develop an effective marketing strategy?  Based on the insights we've uncovered throughout this process, I'd like to propose the following suggestions:

1. A seasonal or weekend-only membership program may be effective in increasing usage among casual riders during the summer and fall and weekends.
2. The existing payment structure may be altered to make single-use more expensive to casual riders as well as lowering the long-term membership rate to generate more sales and revenue.
3. Offering discounts for longer rides to incentivize casual riders and entice members to ride for longer periods.
4. Marketing campaigns should be conducted during summer at vacation locations that are popular among casual riders


Things to consider:
1. Understanding the age and gender distribution of our members is crucial for evaluating the effectiveness of our current marketing strategy. By analyzing these demographics, we can identify if our targeting is inclusive and has the potential to reach a broader audience.
2. The dataset lacks information on the actual pricing plans offered. Analyzing this data would provide valuable insights into user preferences. We could identify the most popular plans and the extent of their popularity compared to others. Additionally, understanding casual user purchasing and spending behavior would be highly beneficial for optimizing our pricing strategy.
