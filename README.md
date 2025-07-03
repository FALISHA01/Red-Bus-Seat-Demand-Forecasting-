# Red Bus Seat Demand Forecasting

**Date:** July 2025  
**Objective:** Forecast daily seat demand between city pairs using historical data and LightGBM

## Overview

This project applies machine learning to predict bus seat counts across Indian intercity routes. It uses enriched transactional data and calendar-based indicators to capture temporal dynamics and regional differences.

## Key Features

- Merged transactional data for specific day-before-departure (DBD=15) journeys
- Feature engineering using:
  - **Lag features**: 1-day and 3-day seat/search history
  - **Momentum features**: Growth in demand over short windows
  - **Route-level statistics**: Mean, median, std seat count by route
  - **Calendar indicators**: Weekend, holiday, school vacations

## Model

- LightGBM regressor with tuned hyperparameters
- Early stopping used for generalization
- Validation with RMSE metric

## Result

- Achieved low RMSE on validation set
- Generated predictions saved in `final_submission_lag_boosted.csv`

## Future Work

- Integrate dynamic pricing data
- Add external data (weather, festival intensity)
- Deploy as API for real-time seat forecasting
