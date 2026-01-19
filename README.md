# Predicting Rain Tomorrow in Fitchburg, MA

## Overview
This project uses logistic regression to predict whether it will rain tomorrow in Fitchburg, Massachusetts, based on current weather conditions and atmospheric measurements available by 4pm today.

## Project Goal
Develop a binary classification model that can predict next-day rainfall using only same-day weather observations, enabling practical short-term forecasting for daily planning decisions.

## Dataset
- **Source**: Historical hourly weather data for Fitchburg, MA (1940-2025)
- **Observations**: 85 years of weather data aggregated to daily summaries
- **Time Period**: 1940-2025
- **Training Data**: Years not divisible by 5 (~80%)
- **Test Data**: Every 5th year (1950, 1955, 1960, etc., ~20%)

## Key Variables
**Response Variable:**
- `rain_tomorrow`: Binary indicator (1 = rain, 0 = no rain) for next day

**Predictors (measured by 4pm today):**
- Current precipitation status
- Atmospheric pressure and pressure changes
- Temperature and humidity at 4pm
- Cloud cover changes throughout the day
- Wind direction (categorical: N, NE, E, SE, S, SW, W, NW)
- Season

## Methodology
- **Model Type**: Logistic Regression
- **Feature Engineering**: 
  - Binary variables for precipitation and rain
  - Change variables (pressure, humidity, temperature, cloud cover from start of day to 4pm)
  - Categorical encoding of wind direction
  - Seasonal variables
  - Interaction terms (e.g., winter × humidity × temperature)

## Model Performance
- **Accuracy**: ~68%
- **ROC AUC**: 0.76
- **Sensitivity**: ~66% (correctly identifies rain days)
- **Specificity**: ~70% (correctly identifies no-rain days)

## Key Findings
- Pressure changes and humidity at 4pm are strong predictors
- Cloud cover changes provide significant signal
- Winter conditions interact with temperature and humidity
- Model performs reasonably well for next-day forecasting

## Technologies Used
- **R** (4.4.0)
- **tidyverse** - Data manipulation and visualization
- **tidymodels** - Model building and evaluation
- **lubridate** - Date/time handling

## How to Run
1. Clone the repository
2. Install required packages: `install.packages(c("tidyverse", "tidymodels", "lubridate"))`
3. Run `RainTomorrow_analysis.qmd` to view methods and codes
4. Open and render `RainTomorrow_report.qmd` for complete analysis

## Author
Evan Pritchard
- Dual Degrees Mathematics and Computer Science, Fitchburg State University
- parachuteriggerwf4@gmail.com
- github.com/ProfessorChaosTheory

## Acknowledgments
- Weather data sourced from Open-Meteo
- Wrangling assisted by Claude AI (Anthropic)
- Project completed as part of MATH 3003 - Advanced Statistics
