# PyBer_Analysis Deliverables

## Overview of Analysis

### 
Upon joining the pseudo ride-sharing company named PyBer, I was tasked to use the pandas library to read in two large .csv datasets into dataframes and merge them into one dataframe for further analysis. The complete parent dataframe contained the columns: city, date, fare, ride_id, driver_count, and type. From the parent dataframe columns, new dataframes were created to be able to track metrics, obtain measures of central tendency, and plot meaningful, visual data. 7 figures were created for the ride-sharing analysis as seen below. For the challenge, 1 screenshot of the ride-sharing data summary dataframe, and 1 Figure for the "Total Fare by City Type." for the dates of 01/01/2019 to 04/28/2019 are also included below under the "Challenge Assignment" headline.

## Results with Figures

### Figure 1.
A bubble chart was created that overlayed three bubble charts into one, containing: y-axis as "Average Fare ($)", x-axis as "Total Number of Rides (Per City)", title: "PyBer Ride-Sharing Data (2019)", a legend with a title of "City Types," for the three color specific city types (Urban, Suburban, Rural), and a chart note of "Note: Circle size correlates with driver count per city." The figure shows that less rides are expected in rural cities, more rides than rural rides in suburban cities, and the most rides given in urban cities. The figure also shows that there is a correlation between average fare ($) per ride and city type, where the most expensive fares are in rural cities and the least expensive rides are in urban cities.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/a4167dfe92cc4c339840c20f49fcb79f72133572/analysis/Fig1.png)

### Figure 2.
Ride count data (2019) for different city types. Urban cities account for the most rides, followed by suburban cities, with rural cities having the least rides given.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/babc1eff02d20967596ba9fd73dc074d7042d797/analysis/Fig2.png)

### Figure 3.
Ride fare data in $USD for different city types. Figure 3, when compared to Figure 2, shows the inverse relationship between number of rides and average fare, where rural cities with the least number of rides have the highest fare cost, and urban cities having the highest number of rides has the lowest fare costs.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/babc1eff02d20967596ba9fd73dc074d7042d797/analysis/Fig3.png)

### Figure 4.
Driver count data (2019) for different city types. Figure 4 shows the relationship between city type and the number of drivers. When compared to Figure 2, the positive correlation between number of drivers and number of rides given can be seen between different city types.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/babc1eff02d20967596ba9fd73dc074d7042d797/analysis/Fig4.png)

### Figure 5.
Percentage of total fares by different city types. Urban cities represent the largest percentage and is in exploded view.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/babc1eff02d20967596ba9fd73dc074d7042d797/analysis/Fig5.png)

### Figure 6.
Percentage of total rides by different city types. Urban cities represent the largest percentage and is in exploded view.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/babc1eff02d20967596ba9fd73dc074d7042d797/analysis/Fig6.png)

### Figure 7.
Percentage of total drivers by different city types. Urban cities represent the largest percentage and is in exploded view.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/babc1eff02d20967596ba9fd73dc074d7042d797/analysis/Fig7.png)

## Challenge Assignment

### 
To round off this PyBer company assignment, we were tasked to create a summary dataframe of the ride-sharing data by city type as well as create a multiple-line graph that showed the total weekly fares for each city type within the specific date range of 01/01/2019 to 04/28/2019.

### Figure 8. 
Ride-Sharing Data By City Type Summary DataFrame. Fare columns are formatted to 2 decimal places.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/ae50900f91bd8d80b442610a111b8e2e41449e02/ride_sharing_summary_df.png)

### Figure 9.
Total fare by city type.

![image](https://github.com/derekhuggens/PyBer_Analysis/blob/babc1eff02d20967596ba9fd73dc074d7042d797/analysis/PyBer_fare_summary.png)

##
Summary
###
Three Business Recommendations to the CEO for addressing disparities among different city types.

  1. Focusing on rural cities' total driver % ratio: 

RURAL VS. SUBURBAN: There is 4.5 times greater % total fares in suburban cities vs. rural and 5 times % total rides in suburban cities vs. rural. When comparing % total drivers by city type between rural and suburban, the disparity grows to there being 6.3 times more drivers in suburban cities than rural cities. 

RURAL VS. URBAN: When comparing % of total fares between rural and urban cities, there is 9.2 times % total fares in urban cities vs. rural cities. When comparing % of total rides between city types, there are 12.9 times more rides in urban cities than rural cities. The disparity in the ratio of % total drivers by city type is seen most when comparing urban and rural, where there are 31.1 times more drivers in urban cities than rural cities. 

If rural cities were marketed to, to recruit more drivers, I believe the total fares as well as total rides would increase for rural cities.
  
  2. Variance in ride fare data.

The standard deviation in urban city fares is comparatively larger than suburban and rural cities as seen below in the summary statistics listed. This larger deviation means there are fares that are more spread out from the center, or mean. Standard deviation is sensitive to far left and far right values and I believe the rides with first quartile and below fares should be investigated and modified in a trial to raise profits. The minimum ride fare of $4.05 and large standard deviation of +/-11.74 from the mean of 24.53 led me to this idea.

Summary Statistics of Urban Cities
count    1625.000000
mean       24.525772
std        11.738649
min         4.050000
25%        14.550000
50%        24.640000
75%        34.580000
max        44.970000
Name: fare, dtype: float64

Summary Statistics of Suburban Cities
count    625.000000
mean      30.970128
std       10.677508
min       12.050000
25%       21.970000
50%       30.750000
75%       39.830000
max       49.960000
Name: fare, dtype: float64

Summary Statistics of Rural Cities
count    125.000000
mean      34.623440
std       14.558046
min       10.110000
25%       19.900000
50%       37.050000
75%       47.070000
max       58.550000
Name: fare, dtype: float64
  
  3. Driver count in certain cities and associated wait times.

When looking at the Pyber Ride-Sharing Data (2019) scatterplot (Figure 1), it can be seen that there are some cities that have a high number of rides (further to the right on the x-axis) but the associated bubble is small (city has a small driver count). For example:

    # Get the city that matches 35.
    urban_city_outlier = urban_ride_count[urban_ride_count==35].index[0]
    print(f"{urban_city_outlier} has the third highest rider count.")
    North Jason has the third highest rider count.

The urban city North Jason also has an urban_driver_count from urban_driver_count = urban_cities_df.groupby(["city"]).mean()["driver_count"] of 6. If there are a high number of rides with such few drivers, are the riders dealing with long wait to times to find a driver? How would the number of rides and the average fare change by adding drivers to these relatively smaller driver count cities?
