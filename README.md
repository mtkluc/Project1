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

Chi-Square Test Analysis
Chi-Square Statistic:
The calculated Chi-Square statistic is 1757.86. This value indicates a substantial difference between the observed frequencies (actual data) and the expected frequencies (what we would expect if there was no association between the variables).
P-Value:
The P-value is 0.0000, which is significantly lower than the common significance level of 0.05. This indicates strong evidence against the null hypothesis.
Degrees of Freedom:
The degrees of freedom for this test are 80. This is calculated based on the number of categories (price ranges and airlines) in the contingency table.
Interpretation
Rejecting the Null Hypothesis:
The conclusion from this analysis is to reject the null hypothesis. This suggests that there is a significant association between the price ranges of flights and the airlines operating on the Sydney to Los Angeles route in December 2024.
Implications
1.	Pricing Strategies: Airlines may have different pricing strategies that are influenced by various factors such as demand, competition, or service levels. Understanding these differences can help airlines optimize their pricing.
2.	Travel Planning: For travellers, this information highlights that flight prices can vary significantly by airline within specific price ranges. This can assist in making informed decisions when selecting airlines based on budget preferences.

![Average_Flight_Price_Range_by_Airline](https://github.com/user-attachments/assets/64c6e7d8-b560-4924-ba16-491c9018f568)
Flights from Sydney to Los Angeles (December 2024)
Overview
This analysis focuses on flight prices from Sydney (SYD) to Los Angeles (LAX) for December 2024. The goal is to understand flight availability and pricing trends, helping travellers make informed decisions.
Key Findings
•	Flight Availability:
o	The program checks which days have flights available, helping travellers choose the best dates to fly.
•	Airline Pricing:
o	By comparing prices, travellers can see which airlines offer the best deals.

![Flight_Prices_Sydney_to_LosAngeles_Dec2024](https://github.com/user-attachments/assets/40ba23ea-5854-4d62-8702-e907fdf43b1d)
![Average_Flight_Prices_Dec24_By_Airline](https://github.com/user-attachments/assets/887b155f-d1f0-4001-b731-54fd582e527e)


![Air_Traffic_Scores_LAX_2018](https://github.com/user-attachments/assets/76a7025f-d966-4377-b3a9-b01ea979729b)

In conclusion, travelling like a local means flying domestic. New York and Chicago may represent interesting destinations to visit. It is unclear why, but from someone who has only heard of pizza from both places, further data analysis may benefit from a food focus.
##

## Key Recommendations based on Data

- Flights in the USA appear most efficient in Autumn, away from holidays.
- LAX appears to experience more delays than the other airports reviewed.
- Travelling like a local means travelling domestic!
- Weather causes the most delays and cancellations in Spring and Summer in the USA.
- Avoid travelling in July and May as weather patterns are unpredictable.
- January and March are the busiest travel months, avoid if you don't like the crowds.
- Flghts are cheapest at the start of December (Fiji Airways was cheapest! (At least if you're from Sydney))



 
