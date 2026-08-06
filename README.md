# Delhi AQI Spatial Analysis
 
Seasonal PM2.5 trends across 6 Delhi monitoring stations, with weather correlation analysis and QGIS station mapping.
 
## Overview
 
This project analyzes how PM2.5 concentrations vary by season and correlate with weather conditions (wind speed, temperature, humidity, pressure) across 6 air quality monitoring stations in Delhi, with spatial mapping of station locations by district using QGIS.
 
## Key Findings
 
 
- Winter PM2.5 averaged **109.28 µg/m³**, compared to **63.58 µg/m³** in monsoon — a **1.72x** difference.
- PM2.5 showed a **negative, weak** correlation with wind speed **within each season** (pooled correlation across seasons was avoided as it conflates seasonal and physical effects — see Methodology).
- **Northern stations**(Anand Vihar,Connaught Place,Rohini) consistently recorded the max PM2.5 (**443.3**), likely due to **proximity to traffic corridor and dry season in summer**.
- Built a **linear regression model** (temperature, humidity, wind speed, pressure → PM2.5); weather variables jointly explained only ~17% of variance (R² = 0.174), with temperature the strongest single predictor — indicating non-meteorological sources (traffic, construction, crop-residue burning) are the dominant drivers of Delhi's PM2.5, not weather alone.
## Data Source
 
- Dataset: delhi-weather-aqi-2025.csv : https://www.kaggle.com/datasets/sohails07/delhi-weather-and-aqi-dataset-2025?select=delhi-weather-aqi-2025.csv
- License: **MIT**
- Coverage: 6 stations — Anand Vihar, Connaught Place, Rohini, Dwarka, IGI Airport, Okhla Phase III
- Time range: **01/01/2025 to 31/12/2025**
- Variables: PM2.5, PM10, aqi, co, no2, temperature, humidity, wind speed, pressure, station location
## Methodology
 
1. Cleaned raw dataset (handled missing values, corrected data types for date/time fields).
2. Grouped records by season — Winter, Summer, Monsoon, Post-Monsoon — based on month.
3. Visualized PM2.5 trends over time and by season using Seaborn (time-series plot, seasonal boxplot).
4. Mapped station locations by district in QGIS and exported as a static PNG.

