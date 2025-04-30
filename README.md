# Bike Sharing Demand Analysis & Prediction 🚴♂️📊

## 🌟 Project Overview
This project compares machine learning and deep learning approaches for predicting bike rental demand using historical data from a bike-sharing system. The analysis covers both daily (`day.csv`) and hourly (`hour.csv`) datasets to identify patterns and build accurate forecasting models.

![Bike Sharing Analysis](https://github.com/HossamElsrah/Northwind-Analysis-Project/blob/main/Reporting/1.png)

## 🔍 Key Features
- **Dual Dataset Analysis**: 731 daily records (2011-2012) and 17,379 hourly records
- **Multi-Target Prediction**: 
  - Casual users
  - Registered users 
  - Total rentals (`cnt`)
- **Comparative Modeling**: 
  - 5 ML models (Linear Regression, SVR, Decision Tree, Random Forest, XGBoost)
  - Deep Learning (Keras Tuner-optimized neural network)

## 🛠️ Technologies Used
### Data Processing & Analysis
- **SQL**: Data exploration and cleaning
- **Pandas**: Feature engineering and transformation
- **NumPy**: Numerical computations

### Machine Learning
- **Scikit-learn**: 
  - Linear Regression, SVR, Decision Trees, Random Forest
  - Hyperparameter tuning with `GridSearchCV`
- **XGBoost**: Gradient boosted trees

### Deep Learning
- **TensorFlow/Keras**: 
  - 3-layer neural network architecture
  - Hyperparameter optimization with Keras Tuner
  - Early stopping and validation monitoring

### Visualization
- **Matplotlib/Seaborn**: Static visualizations
- **Plotly**: Interactive time-series analysis

## 📈 Key Insights
### Demand Patterns
1. **Peak Hours**: 
   - Registered users: 8 AM & 4-7 PM (commute times)
   - Casual users: 10 AM-7 PM (leisure usage)
2. **Seasonality**: 
   - 60% higher demand in Summer/Fall vs Winter
3. **Weather Impact**: 
   - 35% demand drop during heavy rain/snow

### User Behavior
- Registered users account for **81%** of total rentals
- Casual users show higher variance in rental patterns

## 🏗️ Project Structure
```
Bike-Sharing-Analysis/
├── Data/
│   ├── day.csv            # Daily aggregates
│   └── hour.csv           # Hourly records
├── Notebooks/
│   └── Bike_Sharing_Analysis.ipynb  # Complete analysis pipeline
├── Models/
│   ├── best_ml_model.pkl  # Serialized ML model
│   └── keras_model.h5     # Saved DL model
└── Reports/
    ├── EDA_Report.pdf     # Exploratory findings
    └── Model_Comparison.xlsx  # Performance metrics
```

## 🚀 How to Use
1. **Data Preparation**:
   ```python
   # Convert categorical features
   df['season'] = df['season'].map({1:'Spring', 2:'Summer', 3:'Fall', 4:'Winter'})
   ```

2. **Run ML Models**:
   ```python
   from sklearn.ensemble import RandomForestRegressor
   model = RandomForestRegressor(n_estimators=100, max_depth=10)
   model.fit(X_train, y_train)
   ```

3. **Train Neural Network**:
   ```python
   model = Sequential([
       Dense(128, activation='relu', input_shape=(X_train.shape[1],)),
       Dense(64, activation='relu'),
       Dense(2)  # Dual output for casual+registered
   ])
   model.compile(optimizer='adam', loss='mse')
   ```

## 📊 Model Performance
| Model Type          | Daily R² | Hourly R² | Inference Speed |
|---------------------|----------|-----------|-----------------|
| XGBoost (Best ML)   | 0.87     | 0.89      | ⚡ Fast          |
| Neural Network      | 0.81     | 0.86      | ⏳ Moderate      |
| Random Forest       | 0.82     | 0.85      | ⚡ Fast          |

## 💡 Recommendations
1. **Inventory Management**: Increase bike availability during commute hours
2. **Dynamic Pricing**: Higher rates during peak demand periods
3. **Marketing Focus**: Target casual users on weekends/evenings

## 👨💻 Connect
For collaboration or questions:  
[Hossam Taha on LinkedIn](https://linkedin.com/in/hossam-taha-41b724288)
