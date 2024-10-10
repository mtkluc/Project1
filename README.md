# The "SMART" Project 
– Strategic Minimization of Airfare and Risk of Travel delays

## Team Contributions
This project is developed by:

Rajani, Mike and Mandeep

## Overview

This project analyzes flight data using the Amadeus, Meteomatics and BTS APIs to determine the percentage of flights that leave on time, seasonal variations in flight performance, and the impact of external factors such as weather and school holidays. The project also identifies popular travel destinations for locals and the cheapest flights available for top destinations.

## Introduction

We all have kids and are keen travellers. The biggest issue is with delays at airports, and trying to manage kids whilst flying. Not to mention the lack of compensation Australian airlines provide for these inconveniences. We sought to use publically available APIs to try and map delays and to travel smarter. 

## Features

- Analyze on-time performance of flights.
- Assess variations in flight performance by month.
- Examine the impact of school holidays (December-January, Easter, Winter break) on delays.
- Investigate the relationship between weather conditions and flight delays.
- Identify popular destinations for local travelers.
- Determine the cheapest flights for the month of December 2024.
- Find the busiest month of the year.

## Data Collection
The project uses the Amadeus, Meteomatics, BTS APIs to fetch flight data. The data is collected for various months throughout the year to analyze on-time performance and travel trends.

## Analysis
- On-Time Performance: The percentage of flights that leave on time is calculated and displayed.
- Seasonal Variations: The analysis identifies which months have the best on-time performance.
- Impact of Holidays: The project examines delays during significant holiday periods.
- Weather Influence: A weather API can be integrated to analyze its impact on flight delays.
- Local Travel Trends: The project analyzes popular destinations and flight costs for locals.

## Key Questions
Using the data available to us, we tried to answer the following questions
- How often are flights delayed?
- Does time of year or key holiday periods contribute to delays?
- Where do the locals go? Domestic or international?
- How do weather patterns impact delays?
- What are the busiest periods for travel?
- Given we are keen to fly soon, when are the cheapest prices in December for a flight to the USA?

## Flight Delays
We utilised Amadeus' predictive AI tool (as per their notes uses their historical data) to estimate potential flight delays. 
We are aware of the biases in the data, and aware that this data is much more representative of airports located within the USA.

Over the course of the year, the AI predictive tool estimated that flights generally leave on time 70-80% of the time from the airports reviewed (LAX/DEN/DFW/MEL).

![mean_flights_ontime2](https://github.com/user-attachments/assets/be0d8c21-0d82-4ef6-b3f9-c853757b5770)

Fig. showing mean estimated flights leaving on time for the year of 2025.

![flights_ontime_daily](https://github.com/user-attachments/assets/8bc2b58d-0431-41fa-b01e-0beb2431409f)

Fig. flights leaving on time daily over 2025

One-Way ANOVA analysis suggests that there is a significant difference between some of the pairs reviewed, indicating that there delays can be airport specific. 
(F-statistic 101.32, p= 1.43 x e^-59)

Furthermore, when grouped by airport and month, a heatmap reveals differences between the airports and performance by month. It is clear that LAX is predicted to have more delays in general than other airports. The reasons for this remain unclear, but given all three US airports analysed are large, it may reflect more challenging conditions when flying around LAX, or the airlines that provide a service at LAX. Further analysis is recommended to review this, also I am unable to review the underlying model provided by Amadeus which may contain biases. 
Specifically for flying periods with low delays, it would appear the period from February to April, and similarly September to November are predicted to experience less delays. This may be due to it being the shoulder season around major flying with less activity around the airport. We could not locate activity data for this period to confirm. 

![heatmap_flights_ontime](https://github.com/user-attachments/assets/112a3a12-62ca-4ef9-b2d0-3dab31c509ff)

Fig. Heat map of flight delays by month and airports.

To answer the question of holiday periods inducing delays, we segregated the data by month - labelling December, April and July as key holiday months. Analysis indicates that there is an increase in delays by up to 3.5% during the holiday periods depending on the airport. Interestingly LAX showed very little variation in predicted performance between these periods. Given the predictive model indicates a small difference, and the data being utilised to calculate this being small - it is hard to estimate versus the potential true population.

![holiday_vs_non_holiday](https://github.com/user-attachments/assets/5ec07f10-64c2-45da-bbff-5cf5b402f26d)

Fig. Holiday vs Non-Holiday period - flights leaving on time.

![non_holiday_improvement](https://github.com/user-attachments/assets/a268964c-9129-47c5-860a-a707a165e3e4)

Fig. Improvement in flights leaving on time in the non-holiday period vs holiday period.

In conclusion, try to avoid the holiday period where possible if minimising flight delay is important to you. LAX may have other reasons for being the airport experiencing more frequent delays than other airports, but there may be bias in the predictive modelling. 

## Local flight destination popularity
An ideal holiday often does include participating in local activities. We sought to identify the popular local destinations from our chosen airports; however the API chosen only had information from 2018 and a limited number of airports. It would appear the vast majority of flights leaving from the US airports are domestic flights, with only LON (London), CUN (Cancun) and GDL (Guardalajara) being the only international destinations making the top 5 visited destinations in any given month in 2018.

![top_dest_2018](https://github.com/user-attachments/assets/5d0d60d4-30de-4931-8c47-2c8a012c57bf)

Fig. Top Destinations from LAX/DFW/DEN over 2018. Taken from the top 5 destinations each month.

New York and Chicago represented the most popular destinations. We had no data to suggest why this was the case, it could be hypothesized this is due to corporate travel, or possibly that these are local tourist hubs. This data is from pre-COVID and may not be reflective of travel at the current time of writing given how the travel landscape has changed.

![overall_top_dest_2018](https://github.com/user-attachments/assets/7b057bf1-bbd5-4a32-bbc0-41e02a01a7dd)

Fig. Showing overall frequency of destinations from LAX/DEN and DFW.
In conclusion, travelling like a local means flying domestic. New York and Chicago may represent interesting destinations to visit. It is unclear why, but from someone who has only heard of pizza from both places, further data analysis may benefit from a food focus.



# Chi-Square Test Analysis
Chi-Square Statistic:
The calculated Chi-Square statistic is 1757.86. This value indicates a substantial difference between the observed frequencies (actual data) and the expected frequencies (what we would expect if there was no association between the variables).
P-Value:
The P-value is 0.0000, which is significantly lower than the common significance level of 0.05. This indicates strong evidence against the null hypothesis.
Degrees of Freedom:
The degrees of freedom for this test are 80. This is calculated based on the number of categories (price ranges and airlines) in the contingency table.
Interpretation
Rejecting the Null Hypothesis:
The conclusion from this analysis is to reject the null hypothesis. This suggests that there is a significant association between the price ranges of flights and the airlines operating on the Sydney to Los Angeles route in December 2024.
# Implications
1.	Pricing Strategies: Airlines may have different pricing strategies that are influenced by various factors such as demand, competition, or service levels. Understanding these differences can help airlines optimize their pricing.
2.	Travel Planning: For travellers, this information highlights that flight prices can vary significantly by airline within specific price ranges. This can assist in making informed decisions when selecting airlines based on budget preferences.

![Average_Flight_Price_Range_by_Airline](https://github.com/user-attachments/assets/64c6e7d8-b560-4924-ba16-491c9018f568)
Flights from Sydney to Los Angeles (December 2024)
# Overview
This analysis focuses on flight prices from Sydney (SYD) to Los Angeles (LAX) for December 2024. 
The goal is to understand flight availability and pricing trends, helping travellers make informed decisions.

# Key Findings
•	Flight Availability:
The program checks which days have flights available, helping travellers choose the best dates to fly.
•	Airline Pricing:
By comparing prices, travellers can see which airlines offer the best deals.

# Linear Regression Analysis of Flight Prices from Sydney to Los Angeles (December 2024)
Overview
A linear regression analysis was performed to evaluate the relationship between flight prices and the corresponding departure dates from Sydney (SYD) to Los Angeles (LAX) in December 2024. This analysis helps identify trends in pricing over the month.

# Key Findings
Trend: The regression line indicates an upward trend in flight prices, suggesting that as the departure date approaches, prices tend to increase.
Implications: This trend may reflect seasonal demand, where prices rise closer to peak travel times, making it essential for travelers to book flights in advance to secure better rates.
Visualization
A scatter plot with a regression line was created to illustrate the relationship between departure dates and flight prices. The scatter points represent individual flight prices, while the regression line highlights the overall trend.
# Conclusion
The analysis suggests that travelers looking to fly from Sydney to Los Angeles in December 2024 should consider booking early to avoid higher prices as the travel date approaches. Understanding this pricing trend can aid in effective travel planning and budgeting.
![Flight_Prices_Sydney_to_LosAngeles_Dec2024](https://github.com/user-attachments/assets/40ba23ea-5854-4d62-8702-e907fdf43b1d)
![Average_Flight_Prices_Dec24_By_Airline](https://github.com/user-attachments/assets/887b155f-d1f0-4001-b731-54fd582e527e)

Air Traffic Score Analysis for Los Angeles (LAX) in 2018
# Overview
This analysis reviews the air traffic scores at Los Angeles International Airport (LAX) for select months in 2018, highlighting periods of high traveler volume.

# Key Findings
Traffic Scores: The scores indicate traveler activity at LAX, with higher values representing greater airport congestion.
Peak Months: The analysis identifies the months with the highest traffic scores, helping travelers understand when the airport is busiest.
Monthly Air Traffic Scores for 2018
Month	Traffic Score
2018-01	33
2018-02	34
2018-03	32

# Conclusion
February 2018 recorded the highest traffic score of 34, indicating it was a particularly busy month for travel at LAX.
January 2018 followed closely with a score of 33, while March 2018 had a slightly lower score of 32.
Travelers should consider these findings when planning trips to Los Angeles, as traveling during these peak months may lead to increased congestion and longer wait times at the airport. For a more comfortable experience, selecting less busy months could be beneficial.

![Air_Traffic_Scores_LAX_2018](https://github.com/user-attachments/assets/76a7025f-d966-4377-b3a9-b01ea979729b)

## Weather Analysis Based on U.S. Bureau of Transportation Statistics (BTS) Dataset for January 2024:

# 1.	Monthly Weather-Related Delays by Airport:
•	The first chart shows a clear difference in the number of weather-related delays across various airports. Dallas/Fort Worth (DFW) experiences the highest number of delays, peaking sharply in May with over 700 delays.
•	Other airports like JFK, LAX, and SFO maintain relatively low and steady levels of weather-related delays throughout the months, with no drastic spikes. This suggests that certain airports are more vulnerable to weather disruptions, possibly due to geographical or regional weather patterns.

![monthly_weather_related_delays_US_airports](https://github.com/user-attachments/assets/114c29ac-a819-4d7b-8686-e0299a7631ab)

# Implications:
 - Airlines operating from DFW need to allocate more resources and contingency plans during the spring, especially in May, to manage the higher likelihood of weather-related delays and cancellations.
 - Airports like JFK, LAX, and SFO, while having fewer disruptions, should still have systems in place for unexpected weather changes, albeit on a smaller scale.
     
# 2.	Comparison of Weather-Related Delays and Cancellations:
•	Weather-related delays and cancellations exhibit different patterns. May stands out with the highest number of cancellations (over 2000), which could be due to severe weather conditions such as storms or heavy rain that make cancellations more likely. Delays also peak in May but are generally lower than the number of cancellations.
•	The sharp decline in both delays and cancellations in June, followed by another rise in cancellations in July, indicates fluctuating weather conditions that heavily impact flight schedules.
![monthly_weather_related_delays](https://github.com/user-attachments/assets/da7c1b6c-321e-4265-8158-9f46555c8372)
# Implications:
- Passengers flying through DFW in the spring should be prepared for possible delays or cancellations. Awareness campaigns, better communication, and real-time updates can improve customer experience during peak disruption periods.
- Airports with lower disruption rates can focus on maintaining their relatively stable performance by ensuring that smaller disruptions don't escalate.
    
# 3.	Seasonal Analysis of Delays and Cancellations:
•	Weather-related delays and cancellations are highest in the spring season, which could be attributed to volatile weather patterns like thunderstorms and high winds.
•	During the winter season, there are fewer weather-related delays and cancellations, which suggests that while winter storms may cause significant disruptions, they occur less frequently across the U.S.
•	Summer sees a moderate level of disruptions, with cancellations being more prominent than delays, potentially due to unpredictable summer storms.
![seasonal_weather_related_delays_US_airports_2024](https://github.com/user-attachments/assets/3a73d49c-17d6-4a3e-abec-b96e631d5244)
# Implications:
- Airlines should consider adjusting flight schedules and staffing levels during the spring, especially in regions more prone to storms. Flexibility in rebooking and cancellation policies during these peak periods may help reduce passenger dissatisfaction.

To Conclude, these findings highlight the critical importance of weather in flight delays and cancellations, with significant operational and strategic implications for airlines and airport management.

## Five-Day Weather Forecast and Analysis:
# 1.	Correlation Between Weather Conditions:
•	The correlation heatmap shows a very low correlation between temperature and wind speed (0.18), meaning these two factors have little direct interaction. Both variables, however, are independently significant when assessing flight delays. Precipitation data was not available or correlated in this plot, which may need further review to determine its impact on flight operations.
![correlation_weather_coniditions](https://github.com/user-attachments/assets/b7505f3a-43e4-43dc-9f4f-2390c33da008)

# 2.	Wind Speed Impact on Flight Delays/Cancellations:
•	In the first hypothesis analysis, it is evident that higher wind speeds are linked to increased chances of flight delays or cancellations. When wind speeds exceed 5 m/s, the likelihood of delays or cancellations increases, supporting the hypothesis that wind speed is a critical factor in aviation disruptions.
•	Lower wind speeds (below 4 m/s) show negligible effects on delays, indicating that flight operations remain largely unaffected by mild winds
![hypothesis_1](https://github.com/user-attachments/assets/8f2dbc0a-de5b-4d72-8227-a0e373a159d1)
# Implications:
- Airlines and airports should closely monitor wind speed forecasts, especially when speeds exceed 5 m/s, as this is associated with higher chances of delays or cancellations. Contingency plans, such as rescheduling or rerouting flights, can help mitigate the operational impact of high winds.
     
# 3.	Precipitation's Influence on Delays:
•	The second hypothesis examined precipitation and its relationship with flight delays/cancellations. The scatter plot indicates very little to no correlation between precipitation and the chances of delays in the observed data. This could suggest that while precipitation (e.g., rain) may disrupt ground operations or cause delays in specific cases, it is not a dominant factor for widespread flight cancellations or delays across these airports.
![hypothesis_2](https://github.com/user-attachments/assets/15e12468-0677-46dc-8cd6-79422ea2f6d9)
# Implications:
- Despite precipitation's potential to disrupt airport operations, its limited influence on delays in this dataset suggests that airports have established effective management practices for dealing with rain or other precipitation. However, airports should still be vigilant, especially in regions prone to more severe weather (e.g., snow or hail), which could have a greater impact than rain alone.
      
# 4.	Temperature's Impact on Flight Delays/Cancellations:
•	The third hypothesis analyzed the relationship between temperature and the likelihood of delays. Similar to wind speed, there seems to be a relationship between higher temperatures and increased delays or cancellations, particularly when temperatures reach the 16°C range. The spread of data suggests that temperature extremes (whether too low or too high) may cause operational challenges leading to delays.
![hypothesis_3](https://github.com/user-attachments/assets/ebc5cf9e-7e60-4f1e-8df1-64564f28ee6e)
# Implications:
- As temperatures rise, particularly in summer months, airlines should prepare for potential delays or equipment challenges. Ground delays due to heat may cause significant logistical issues, requiring adequate planning for fuel management and passenger comfort.
- The findings reinforce the need for more granular predictive models to forecast delays based on weather. By integrating precise weather data with operational metrics, airlines can improve resource allocation, minimize delays, and enhance the passenger experience during disruptive weather events.
# Summary  
wind speed and temperature are the most influential weather factors affecting flight delays and cancellations. Precipitation appears to have a limited effect in this dataset, but further analysis with more diverse weather conditions might reveal a different relationship. Seasonal planning and operational flexibility will be key for mitigating the impact of weather on flight operations.

##

## Key Recommendations based on Data

- Flights in the USA appear most efficient in Autumn, away from holidays.
- LAX appears to experience more delays than the other airports reviewed.
- Travelling like a local means travelling domestic!
- Weather causes the most delays and cancellations in Spring and Summer in the USA.
- Avoid travelling in July and May as weather patterns are unpredictable.
- January and March are the busiest travel months, avoid if you don't like the crowds.
- Flghts are cheapest at the start of December (Fiji Airways was cheapest! (At least if you're from Sydney))



 
