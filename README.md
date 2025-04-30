# Bike Sharing Demand Analysis & Prediction (ML vs DL)

## Project Overview
This project analyzes bike sharing patterns and compares traditional Machine Learning (ML) with Deep Learning (DL) approaches for predicting bike rental demand. The analysis uses two datasets (daily and hourly records) from a bike-sharing system in Washington D.C.

**Key Objectives:**
1. Perform comprehensive EDA to uncover rental patterns
2. Build predictive models for both casual and registered users
3. Compare performance of ML and DL approaches
4. Develop actionable business insights

## Dataset Description
Two datasets are provided with identical features (except hour field):

### Features:
- **Temporal:**
  - `dteday`: Date (YYYY-MM-DD)
  - `season`: 1=Spring, 2=Summer, 3=Fall, 4=Winter
  - `yr`: Year (0=2011, 1=2012)
  - `mnth`: Month (1-12)
  - `hr`: Hour (0-23, only in hourly data)
  - `weekday`: Day of week (0=Sun to 6=Sat)
  
- **Weather:**
  - `weathersit`: 
    - 1: Clear/Few clouds
    - 2: Mist/Cloudy
    - 3: Light Snow/Rain
    - 4: Heavy Rain/Snow
  - `temp`: Normalized temperature (°C)
  - `atemp`: Normalized "feels-like" temperature
  - `hum`: Normalized humidity
  - `windspeed`: Normalized wind speed

- **Usage:**
  - `casual`: Non-registered user rentals
  - `registered`: Registered user rentals
  - `cnt`: Total rentals (casual + registered)

## Key Insights from EDA

### User Behavior Patterns:
- Registered users dominate rentals (4:1 ratio vs casual)
- Strong seasonal patterns - peak demand in Summer/Fall
- Distinct hourly patterns:
  - Registered: Peaks at 8AM & 5PM (commute times)
  - Casual: Steady 10AM-7PM (leisure usage)

### Weather Impact:
- 80% of rentals occur in clear/misty conditions
- Extreme weather reduces rentals by 30-50%

### Growth Trends:
- 2012 saw 15% more rentals than 2011
- Weekday rentals more consistent than weekends

## Modeling Approach

### Data Preparation:
- Removed redundant features (`instant`, `atemp`)
- Converted categorical variables using One-Hot Encoding
- Created separate pipelines for daily/hourly data

### Model Comparison:
| Model Type       | Days Dataset (R²) | Hours Dataset (R²) |
|------------------|-------------------|--------------------|
| Linear Regression| 0.80              | 0.63               |
| SVR              | 0.69              | 0.79               |
| Decision Tree    | 0.85              | 0.90               |
| Random Forest    | 0.98              | 0.99               |
| XGBoost          | 0.99              | 0.97               |
| Neural Network   | 0.81              | 0.86               |

### Best Performing Models:
- **Days Dataset:** XGBoost (99% accuracy)
- **Hours Dataset:** XGBoost (97% accuracy)

## Business Recommendations

1. **User Conversion:**
   - Target casual users with loyalty programs
   - Offer first-ride discounts for registration

2. **Inventory Management:**
   - Increase bike availability during:
     - Summer/Fall months
     - Weekday rush hours (7-9AM, 4-7PM)
   - Reduce inventory during extreme weather

3. **Pricing Strategy:**
   - Dynamic pricing during peak demand periods
   - Weather-based discounts during rain/snow

4. **Service Expansion:**
   - Focus on business districts for morning/evening peaks
   - Expand leisure areas for midday casual usage

## Technical Implementation

### Requirements:
- Python 3.7+
- Libraries:
  - pandas, numpy
  - scikit-learn, xgboost
  - tensorflow/keras
  - matplotlib, seaborn, plotly

### File Structure:
```
/project
│── /data
│   ├── day.csv
│   └── hour.csv
│── Bike_Sharing_Analysis_&_Prediction_(ML_VS_DL).ipynb
└── README.md
```

## Future Enhancements
- Implement real-time demand forecasting
- Add weather API integration for live predictions
- Develop user segmentation models
- Create anomaly detection for maintenance planning

## Connect
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/hossam-taha-41b724288)

**Hossam Taha**  
Data Science & AI Specialist
