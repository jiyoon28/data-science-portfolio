# Bike Share Trip Data Analysis

## Project Overview

This project analyzes the FordGoBike (Bay Wheels) trip data from February 2019 to uncover usage patterns and trends in the San Francisco Bay Area bike-sharing system. The analysis follows a structured approach with data wrangling and exploratory visualization phases.

---

## Objectives

- Clean and prepare bike trip data for analysis
- Explore trip duration patterns across different user segments
- Analyze geographic distribution of bike stations
- Identify temporal trends in bike usage
- Compare behavior between subscribers and casual customers

---

## Key Findings

- **User Demographics**: Subscribers dominate the user base, primarily using bikes for shorter, consistent commute trips
- **Peak Usage**: Morning (8-9 AM) and evening (5-6 PM) commute hours show highest trip frequency
- **Trip Duration**: Casual customers tend to take longer trips than subscribers
- **Gender Distribution**: Male users represent the majority of recorded trips
- **Geographic Hotspots**: BART stations and downtown areas are the most popular start/end locations

---

## Project Structure

| File | Description |
|------|-------------|
| Part_I_data_wrangling.ipynb | Data loading, cleaning, and feature engineering |
| Part_II_data_visualization.ipynb | Exploratory data analysis with visualizations |

---

## Technologies Used

- **Language**: Python 3.x
- **Libraries**: pandas, numpy, matplotlib, seaborn
- **Environment**: Jupyter Notebook

---

## Dataset

- **Source**: FordGoBike System Data (February 2019)
- **Records**: ~180,000+ trip records
- **Features**: Trip duration, start/end times, station information, user type, member demographics