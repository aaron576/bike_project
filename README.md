# README.md

## NYC Bike Rental: An Analysis of Ridership vs. Weather

This project explores the relationship between weather conditions and bike share ridership in New York City from August 2024 to August 2025. Using public data from CitiBikeNYC and historical weather data, this analysis aims to identify the key factors that influence rental demand and uncover different patterns of usage between annual members and casual riders.

## Data Sources
- Bike Data: https://citibikenyc.com/system-data
- Weather Data: Sourced via the Meteostat Python library

## How to run this notebook

1. Clone this repo

2. Navigate to project folder

3. From the Bike Data source download JC-202408-citibike-tripdata.csv.zip through JC-202508-citibike-tripdata.csv.zip. Extract them into /data/raw. Alternatively I provided the data in a zip file under releases.

4. create and activate a virtual environment

5. Install the required packages

`pip install -r requirements.txt`

6. Open bike_project.ipynb

7. Run all

# Conclusions

This analysis of NYC bike rental data indicates a strong correlation between ridership and weather patterns, with daily ride counts tending to increase with warmer temperatures. Usage patterns also show clear variations across the day and week, with distinct peaks that align with typical weekday commuting hours. Furthermore, the data highlights a significant difference in usage behavior between casual riders and annual members, most notably in their average trip durations. These observations suggest that weather, commuting schedules, and user type are key factors associated with how the bike share service is used.

## Key Findings

- Strong Correlation with Weather: The analysis reveals a strong, positive correlation (r=0.79) between the average daily temperature and the number of rides. Conversely, there is a negative correlation with precipitation. This suggests that pleasant weather is a significant factor associated with higher ridership.

- Distinct Weekday Commuting Patterns: Hourly usage data shows two primary peaks during weekdays, at 8 AM and 5-6 PM, which strongly suggests the service is a popular option for commuting to and from work.

- Different Usage by Rider Type: Casual riders, on average, take significantly longer trips than members. This may indicate different primary use cases between the groups, with members potentially using the service for efficient, shorter trips while casual riders engage in more leisurely rides.

- Geographic Concentration of Demand: A small number of stations, particularly those near major transit hubs like Grove St PATH and Hoboken Terminal, account for a disproportionately high volume of ride starts. This indicates these locations are critical points in the network.
- Statistical testing revealed that the presence of missing data is not random but has a significant association with the user type.

## Model-Driven Conclusions

- The linear regression and Poisson general regression models validates that weather is a primary predictive driver for ridership.

- The analysis successfully quantifies the impact of key weather variables, demonstrating a strong positive correlation with temperature (~81 additional rides per +1°C) and a significant negative correlation with precipitation (~41 fewer rides per mm of rain).

- This predictive model serves as a practical tool for demand forecasting, enabling more proactive operational strategies, such as optimizing bike redistribution based on upcoming weather forecasts.

## Actionable Insights

Based on the correlations observed in the data, the following strategic opportunities could be considered:

- Targeted Marketing Opportunities: Given the different ride duration patterns, marketing efforts could be tailored. For example, campaigns targeting casual users might promote "weekend sightseeing routes," while member-focused content could emphasize the service's reliability and efficiency for daily commutes.

- Optimized Bike Distribution: The station popularity data can inform logistical strategies. Ensuring higher bike availability at the busiest stations just before the morning and evening commute peaks could enhance service reliability and potentially increase customer satisfaction.

- Demand Management Strategies: To help mitigate the observed drop in ridership on days with poor weather, the service could explore piloting a dynamic pricing model, such as offering "rainy day discounts" to incentivize use during off-peak conditions.

## Key Visualizations

<table>
  <tr>
    <td><img src="reports/dual_axis_plot.png" alt="Image 1"></td>
    <td><img src="reports/violin_plot.png" alt="Image 2"></td>
    <td><img src="reports/correlation_heatmap.png" alt="Image 3"></td>
    <td><img src="reports/actual_vs_predicted.png" alt="Image 3"></td>
  </tr>
</table>


![Daily Rides vs. Temperature](reports/dual_axis_plot.png)

![Member vs. Casual Ride Durations](reports/violin_plot.png)

![Correlation Heatmap](reports/correlation_heatmap.png)

![Linear Regression](reports/actual_vs_predicted.png)
