# Shoe Replacement Prediction Model 👟

This machine learning project aims to predict the remaining lifespan of running shoes using user activity data exported from Strava.

## Project Overview
Running shoes have a limited lifespan (typically around 800km / 500 miles). Tracking this mileage manually across different activities can be tedious. This project automates the process by analyzing Strava running data, calculating cumulative distance, and predicting the remaining distance before a shoe replacement is required.

## Data
The dataset consists of Strava activity data, including:
- Activity type (Run, Walk, Workout, etc.)
- Distance per activity
- Moving time and Elapsed time
- Average speed, max speed, and elevation gain

*(Note: Personal data files are excluded from this repository via `.gitignore` for privacy)*

## Machine Learning Models
Two models were developed and compared for this task:
1. **Linear Regression**: A robust baseline model using cumulative 'Total Distance' to predict 'Remaining Distance'.
2. **Random Forest Regressor**: A more complex ensemble model exploring the impact of additional features like average speed and activity type.

## Project Structure
```text
shoe_replacement_prediction/
├── data/                  # Raw and processed datasets (ignored in git)
├── notebooks/             # Jupyter notebooks for EDA and model prototyping
├── models/                # Saved model binaries
├── src/                   # Reusable source code
│   ├── features/          # Feature engineering scripts
│   ├── models/            # Model definition and training scripts
│   └── utils/             # Utility functions
├── .gitignore             # Files to hide from Git (e.g., personal data, pycache)
└── README.md              # Project description
```

## Results & Insights
- **Exploratory Data Analysis (EDA)**: Conducted to visualize the distribution of running distances, activity types, and average speeds.
- **Feature Importance**: Correlation heatmaps and Random Forest feature importance analysis confirmed that cumulative `Total Distance` is the absolute primary predictor for shoe lifespan, acting as a deterministic feature.
- **Performance**: The models successfully captured the degradation curve of the shoes, resulting in highly accurate predictions based on the 800km maximum lifespan baseline.