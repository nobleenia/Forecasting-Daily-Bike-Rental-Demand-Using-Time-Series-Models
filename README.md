# Forecasting Daily Bike Rental Demand Using Time Series Models

## Overview
This project focuses on analyzing and forecasting daily bike rental demand for a bike rental company. Using real-world data from the Capital Bikeshare system, we applied various data analysis and time series modeling techniques to uncover patterns, identify key factors influencing demand, and forecast future rentals. The goal is to support business decision-making related to fleet management, pricing strategies, and operational efficiency.

---

## Project Objectives
1. **Describe and explore the data** to uncover trends, seasonality, and key influencing factors.
2. **Fit well-validated time series models** (e.g., ARIMA) to forecast future bike rental demand.
3. **Provide actionable insights and data-driven recommendations** to optimize fleet management and pricing.

---

## Dataset Description
The dataset includes daily and hourly records of bike rentals in Washington, D.C., collected over 2011 and 2012. It also includes environmental and seasonal variables such as temperature, humidity, and weather conditions.

### Files
- **`day.csv`**: Aggregated daily bike rental data.
- **`hour.csv`**: Hourly bike rental data.
- **`Readme.txt`**: Description of the dataset and its attributes.

### Key Variables
1. **`cnt`**: Total bike rentals (sum of `casual` and `registered` users).
2. **`dteday`**: Date of the observation.
3. **`season`**: Season (1: Spring, 2: Summer, 3: Fall, 4: Winter).
4. **`yr`**: Year (0: 2011, 1: 2012).
5. **`temp`**: Normalized temperature in Celsius.
6. **`weathersit`**: Weather situation (1: Clear, 2: Mist, 3: Light Snow/Rain, 4: Heavy Rain/Snow).
7. **`registered`**: Count of registered users.
8. **`casual`**: Count of casual users.

For a detailed description, refer to the `Readme.txt` file provided with the dataset.

---

## Analysis Workflow

### 1. Data Exploration
- Summary statistics and data cleaning were performed to identify missing values, outliers, and correlations.
- Key trends and patterns were visualized, including:
  - Distribution of bike rentals.
  - Seasonal trends and time series plots.

### 2. Time Series Smoothing
- Moving averages (7-day and 30-day) were used to smooth the data and highlight long-term trends.
- Lowess smoothing provided flexible, non-linear fits for better visualization.

### 3. Time Series Decomposition
- The time series was decomposed into trend, seasonal, and residual components to better understand its structure.

### 4. Stationarity and Differencing
- The data was tested for stationarity using the Augmented Dickey-Fuller (ADF) test.
- Differencing was applied to make the series stationary, enabling ARIMA modeling.

### 5. ARIMA Modeling and Forecasting
- An ARIMA model was fitted to the stationary data.
- Residual diagnostics confirmed the model's validity.
- The model was used to forecast the next 30 days of bike rental demand, including confidence intervals.

### 6. Findings and Recommendations
- Insights from the analysis were compiled, focusing on demand patterns, influencing factors, and actionable recommendations.
- Detailed recommendations addressed fleet management, pricing strategies, marketing, and weather-based adjustments.

---

## Key Findings
1. **Seasonality and Growth**:
   - Demand is highly seasonal, peaking in summer and dipping in winter.
   - A general upward trend indicates increasing popularity over the two years.

2. **Influencing Factors**:
   - Rentals are strongly correlated with temperature and registered users.
   - Weather conditions, especially wind and precipitation, negatively impact demand.

3. **Forecasting**:
   - The ARIMA model provided reliable forecasts for the next 30 days, aligning with historical trends.

---

## Recommendations
1. **Fleet Management**:
   - Increase fleet availability during peak seasons (spring/summer) and reduce during winter.
   - Strategically allocate bikes to high-demand locations based on forecasted data.

2. **Dynamic Pricing**:
   - Implement higher pricing during peak demand periods to maximize revenue.
   - Offer promotions during low-demand periods to attract casual riders.

3. **Weather-Based Adjustments**:
   - Reduce fleet deployment during extreme weather.
   - Provide real-time alerts and encourage safe riding practices.

4. **Marketing**:
   - Launch seasonal campaigns to boost awareness and attract new customers.
   - Partner with local events to increase rentals during off-peak times.

---

## Tools and Libraries Used
- **Programming Language**: R
- **Key Libraries**:
  - `tidyverse` for data manipulation and visualization.
  - `forecast` for ARIMA modeling.
  - `timetk` and `plotly` for interactive time series analysis.
  - `ggplot2` for static visualizations.
  - `tseries` for stationarity testing.

---

## Folder Structure
project/
│
├── data/
│   ├── day.csv
│   ├── hour.csv
│   └── Readme.txt
│
├── scripts/
│   └── analysis.R
│
├── results/
│   ├── smoothed_plots/
│   ├── decomposition.png
│   ├── differenced_series.png
│   ├── forecast_plots/
│   └── forecasted_values.csv
│
├── README.md
└── report.Rmd
