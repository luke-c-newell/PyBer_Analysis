# PyBer_Analysis
## Overview
My client has asked me to create a summary DataFrame of ride-sharing data by city type (Rural, Suburban and Urban). In addition, they've asked for a multiple-line graph that shows the total weekly fares for each city type. I've also included a summary of how the data differs by city type and how those differences can be used by decision-makers at PyBer.
## Results
### Summary DataFrame
This DataFrame summarizes the Total Rides, Total Drivers, Total Fares, Average Fare per Ride and  Average Fare per Driver for each city type. See code sample below to understand the method used to create this dataframe.
![City_type_df](https://github.com/luke-c-newell/PyBer_Analysis/blob/main/Resources/city_type_df.png)
### Multiple line chart of total fares by city type
This multiple line chart shows the weekly sum of total fares collected for each city type from January 2019 to April 2019. Urban cities saw the highest revenue for each week, with Rural cities seeing the lowest fares over the same period. See code sample below to understand the method used to create this chart.
![PyBer_fare_summary](https://github.com/luke-c-newell/PyBer_Analysis/blob/main/analysis/PyBer_fare_summary.png)
### Differences between data collected
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
1. 
2. 
3. 
## Code Samples
### Creating the summary dataframe
``` 
ride_count = pyber_data_df.groupby(["type"]).count()["ride_id"]
driver_count = city_data_df.groupby(["type"]).sum()["driver_count"]
fare_total = pyber_data_df.groupby(["type"]).sum()["fare"]
average_fare_ride = fare_total / ride_count
average_fare_driver = fare_total / driver_count
pyber_summary_df = pd.DataFrame(
          {"Total Rides": ride_count,
          "Total Drivers": driver_count,
          "Total Fares": fare_total,
          "Average Fare per Ride": average_fare_ride,
          "Average Fare per Driver": average_fare_driver})
pyber_summary_df.index.name = None
pyber_summary_df["Total Rides"] = pyber_summary_df["Total Rides"].map("{:,}".format)
pyber_summary_df["Total Drivers"] = pyber_summary_df["Total Drivers"].map("{:,}".format)
pyber_summary_df["Total Fares"] = pyber_summary_df["Total Fares"].map("${:,.2f}".format)
pyber_summary_df["Average Fare per Ride"] = pyber_summary_df["Average Fare per Ride"].map("${:.2f}".format)
pyber_summary_df["Average Fare per Driver"] = pyber_summary_df["Average Fare per Driver"].map("${:.2f}".format)
```
### Creating the multiple line chart
```
fare_sum_df = pyber_data_df.groupby(["type", "date"]).sum()["fare"]
fare_sum_df = fare_sum_df.reset_index()
fare_sum_df = fare_sum_df.pivot(index="date", columns="type", values="fare")
jan_apr_df = fare_sum_df.loc['2019-01-01':'2019-04-29']
jan_apr_df.index = pd.to_datetime(jan_apr_df.index)
jan_apr_df_weekly = jan_apr_df.resample("W").sum()

from matplotlib import style

style.use('fivethirtyeight')

jan_apr_df_weekly.plot(figsize=(14, 6))
plt.legend(mode="Expanded", bbox_to_anchor=(1, 1))
plt.xlabel("")
plt.ylabel("Fare ($USD)", fontsize=12)
plt.title("Total Fare by City Type", fontsize=12)

plt.savefig("analysis/PyBer_fare_summary.png",  bbox_inches="tight")
```
