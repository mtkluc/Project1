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

Furthermore, when grouped by airport and month, a heatmap reveals differences between the airports and performance by month. It is clear that LAX is predicted to have more delays in general than other airports. The reasons for this remain unclear, but given all three US airports analysed are large, it may reflect more challenging conditions when flying around LAX, or the airlines that provide a service at LAX. 

![heatmap_flights_ontime](https://github.com/user-attachments/assets/112a3a12-62ca-4ef9-b2d0-3dab31c509ff)


## Key Recommendations based on Data

- Flights in the USA appear most efficient in Autumn, away from holidays.
- LAX appears to experience more delays than the other airports reviewed.
- Travelling like a local means travelling domestic!
- Weather causes the most delays and cancellations in Spring and Summer in the USA.
- Avoid travelling in July and May as weather patterns are unpredictable.
- January and March are the busiest travel months, avoid if you don't like the crowds.
- Flghts are cheapest at the start of December (Fiji Airways was cheapest! (At least if you're from Sydney))



 
