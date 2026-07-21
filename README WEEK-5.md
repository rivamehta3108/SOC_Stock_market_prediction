# Stock Price Prediction Using LSTM

## Overview

This project implements a Long Short-Term Memory (LSTM) neural network to predict future stock prices using historical stock market data downloaded from Yahoo Finance. The user can specify the stock ticker, start date, end date, and timeframe. The model uses Closing Price, MACD, and RSI as input features and predicts the next 15 future periods of stock prices.

---

## Objective

The objective of this project is to:

- Download historical stock market data from Yahoo Finance.
- Visualize stock price trends.
- Calculate and visualize technical indicators.
- Preprocess stock market data for deep learning.
- Train an LSTM model to learn historical patterns.
- Predict the next 15 future stock prices.
- Evaluate model performance using RMSE and R² Score.

---

## Data Collection

The program takes user input for:

```python
stock_name = input("Enter stock ticker: ")
start_date = input("Enter start date: ")
end_date = input("Enter end date: ")
timeframe = input("Enter timeframe: ")
```

Example:

```text
Enter stock ticker: AAPL
Enter start date: 2020-01-01
Enter end date: 2025-01-01
Enter timeframe: 1d
```

The data is downloaded using the yfinance library.

---

## Libraries Used

- yfinance
- numpy
- matplotlib
- tensorflow
- scikit-learn

---

## Technical Indicators Used

### 1. MACD (Moving Average Convergence Divergence)

MACD is a trend-following momentum indicator that shows the relationship between two exponential moving averages of a stock price.

Significance:
- Identifies trend direction.
- Measures momentum.
- Helps detect potential trend reversals.

### 2. RSI (Relative Strength Index)

RSI is a momentum oscillator that measures the speed and magnitude of recent price changes.

Significance:
- Detects overbought conditions (RSI > 70).
- Detects oversold conditions (RSI < 30).
- Measures market momentum.

---

## Data Visualization

The following visualizations were created:

1. Closing Price vs Date
2. MACD and Signal Line
3. RSI Indicator
4. Actual vs Predicted 15-Day Forecast

---

## Data Preprocessing

The following preprocessing steps were performed:

1. Downloaded historical stock data.
2. Calculated MACD and RSI indicators.
3. Removed missing values.
4. Selected the following features:
   - Closing Price
   - MACD
   - RSI
5. Normalized data using MinMaxScaler.
6. Created sliding-window sequences.

### Input Window

The model uses the previous 60 days of data.

### Prediction Horizon

The model predicts the next 15 future stock prices.

---

## LSTM Model Architecture

### First LSTM Layer

- 64 Units
- Return Sequences = True
- Dropout = 0.2

### Second LSTM Layer

- 32 Units
- Return Sequences = False
- Dropout = 0.2

### Dense Layers

- Dense Layer (32 neurons, ReLU activation)
- Output Layer (15 neurons)

### Training Parameters

- Optimizer: Adam
- Loss Function: Mean Squared Error (MSE)
- Epochs: 30
- Batch Size: 32

---

## Model Evaluation

The model performance is evaluated using:

### Root Mean Squared Error (RMSE)

RMSE measures the average prediction error.

Formula:

RMSE = √(Mean Squared Error)

### R² Score

R² Score measures how well the predictions explain the variance in the actual data.

Formula:

R² = 1 − (Σ(y − ŷ)² / Σ(y − mean(y))²)

---

## Results

### RMSE

Replace with your obtained value:

```text
RMSE = 0.07913076554136701

### R² Score

Replace with your obtained value:

```text
R² Score = 0.5727281625383858
```

The model successfully learns historical price patterns and generates forecasts for the next 15 future periods.

---

## Future Forecast

After training, the model uses the most recent 60 days of stock market data to predict the next 15 future stock prices.

The predicted values are displayed and visualized using a forecast graph.

---

## How to Run the Project

### Install Required Libraries

```bash
pip install yfinance numpy matplotlib tensorflow scikit-learn
```

### Run the Notebook

1. Open Jupyter Notebook.
2. Open the project notebook.
3. Run all cells sequentially.
4. Enter the required stock information when prompted.
5. View the generated visualizations and predictions.

---

## Project Structure

```text
Stock-Price-Prediction-LSTM/
│
├── README.md
├── Stock_Price_Prediction.ipynb
│
└── images/
    ├── closing_price.png
    ├── macd.png
    ├── rsi.png
    └── prediction_vs_actual.png
```

---

## Conclusion

This project demonstrates the application of Long Short-Term Memory (LSTM) networks for stock price prediction. By combining historical closing prices with MACD and RSI technical indicators, the model is able to capture both trend and momentum information and generate forecasts for future stock prices. The project highlights how deep learning can be applied to financial time-series forecasting.