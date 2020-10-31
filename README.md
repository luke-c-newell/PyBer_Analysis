# PyBer_Analysis
## Overview
My client, PyBer, a large ride-sharing company, has asked me to create a summary dataframe for ride-sharing data by city type (for rural, suburban and urban cities). In addition, they've asked for a multiple-line graph that shows the total weekly fares for each city type for the months of January through April. I've also included a summary of how the data differs by city type and how these findings can be actioned upon by decision-makers at PyBer.
## Results
### Summary DataFrame
This dataframe summarizes the Total Rides, Total Drivers, Total Fares, Average Fare per Ride and  Average Fare per Driver for each city type. See code found in the PyBer_Challenge file to understand the method used to create this dataframe.

![City_type_df](https://github.com/luke-c-newell/PyBer_Analysis/blob/main/Resources/city_type_df.png)
### Multiple line chart of total fares by city type
This multiple line chart shows the weekly sum of total fares collected for each city type from January 2019 to April 2019. Urban cities saw the highest revenue for each week, with Rural cities seeing the lowest fares over the same period. See code found in the PyBer_Challenge file to understand the method used to create this dataframe.

![PyBer_fare_summary](https://github.com/luke-c-newell/PyBer_Analysis/blob/main/analysis/PyBer_fare_summary.png)
### Differences between data for each city type
1. Total Rides
Rural cities saw the lowest number of total rides with 125 whereas urban cities saw the largest number of rides with 1625 which is 13x larger than the number of rural rides. Suburban cities had 5x more rides than rural cities with 625 total rides. 
2. Total Drivers
Urban cities had the largest number of drivers with 2405 total drivers over the period of the analysis. Suburban cities had 490 drivers but rural cities had the lowest number of drivers with 78.
3. Total Fares
Urban cities had the highest total fares with $39,854, suburban cities had a total fare volume of $19,356 and rural cities had the lowest total fares with $4,327. This trend matches the trend for total rides and total drivers, which all saw urban cities with the largest total volume.
4. Average Fare per Ride
In contrast to the three previous metrics, the largest average fare per ride was in rural cities, with an average fare of $34. Suburban cities had an average fare per ride of $30, with urban cities seeing the lowest average fare at $24.
5. Average Fare per Driver
This trend continued for the average fare per driver, with rural cities again on top with an average fare of $55. Suburban cities had an average fare per driver of $39, with urban cities seeing the lowest average fare per driver of $16.
6. Weekly Total Fares
Urban cities had the highest weekly total fares, with rural cities showing the lowest weekly fares. Urban cities lowest weekly total was $1,661 for w/e Jan 6 with the largest total being $2,470 for w/e Mar 10. Suburban cities lowest weekly total was $721 for w/e Jan 6 with the largest total being $1,412 for w/e Feb 24. Rural cities lowest weekly total was $67 for w/e Jan 13 with the largest total being $501 for w/e Mar 10. 
## Summary
### Recommendations
1. As urban cities are the main driver of revenue for PyBer, they present the greatest opportunity for increasing profit at the company. Despite bringing in the greatest volume of revenue, urban cities have the lowest average fare per ride, which may be a result of a shorter distance travelled for each trip.  I would recommend encouraging urban riders to use the service for longer rides by developing promotions that reward longer trips.
2. Rural cities have the lowest revenue compared to the other city types which presents an opportunity to greatly increase use of the service in rural areas. I would recommend increasing the marketing budget for rural cities to attract both additional customers and drivers to the service. As the number of drivers in rural cities is so low, this may be a limiting factor to increasing the revenue so increasing marketing towards additional drivers is essential. The relatively high average fare per ride of $55 could be used to entice them to sign up as drivers.
3. Suburban cities are in the middle of the road in all six of the metrics analyzed in this report. Despite this, there are still opportunities to increase the numbers of riders when compared with urban cities. As there is an overpopulation of drivers in urban cities, they could be encouraged to travel to suburban cities to take advantage of the higher average fare per ride in suburban areas. This could increase demand for rides in suburban areas that have a lower number of drivers than urban areas.
