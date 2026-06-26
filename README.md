# THYAO Stock Price Prediction using LSTM

This project aims to predict the closing price of Turkish Airlines (THYAO) stock traded on Borsa Istanbul using a Long Short-Term Memory (LSTM) neural network.

The study investigates the application of deep learning techniques to financial time series forecasting and demonstrates how LSTM architectures can capture temporal dependencies in stock market data.

---

## Project Objective

The primary objective of this project is to forecast the next day's closing price of THYAO stock using historical market information.

Since financial time series exhibit nonlinear patterns and temporal dependencies, an LSTM-based deep learning model was preferred over traditional statistical approaches.

---

## Dataset

The dataset consists of daily THYAO stock market data covering the period between **2023 and 2025**.

The following variables were used:

* Open Price
* High Price
* Low Price
* Close Price
* Trading Volume

The original dataset contained **749 observations**. After preprocessing and feature engineering, **730 observations** remained for model training and evaluation.
## Data Source

The dataset used in this project was collected from Yahoo Finance using the `yfinance` Python library.

Ticker Symbol: `THYAO.IS`

Period: January 2023 - January 2025

Source:
https://finance.yahoo.com/quote/THYAO.IS
---

## Feature Engineering

To improve predictive performance, several additional features were created.

### Lag Features

* Close_lag_1
* Close_lag_3
* Close_lag_5
* Close_lag_10

### Moving Averages

* MA_5
* MA_10
* MA_20

### Additional Feature

* Daily Return

All variables were normalized using the **MinMaxScaler** method before training the model.

---

## Model Architecture

The proposed model consists of:

* LSTM layer with 64 units
* Dropout layer
* LSTM layer with 32 units
* Dropout layer
* Dense output layer

Total trainable parameters:

```
32,417
```

### Training Configuration

* Loss Function: Mean Squared Error (MSE)
* Optimizer: Adam
* Maximum Epochs: 100
* Early Stopping: Enabled

Training automatically stopped around the **39th epoch** to prevent overfitting.

---

## Time Window Approach

The model uses the previous **30 trading days** to predict the next day's closing price.

| Property              | Value   |
| --------------------- | ------- |
| Original observations | 749     |
| Final observations    | 730     |
| Window size           | 30 days |
| Number of features    | 13      |
| Total sequences       | 700     |
| Training samples      | 560     |
| Test samples          | 140     |

---

## Model Performance

| Metric | Value  |
| ------ | ------ |
| RMSE   | 8.99   |
| MAE    | 6.83   |
| R²     | 0.8463 |

The model explains approximately **84.6%** of the variation in the test dataset.

---

## Results

* The model successfully captured the overall market trend.
* Upward and downward price movements were identified reasonably well.
* Predictions were smoother than actual prices, especially during highly volatile periods.
* Residual analysis indicated no significant systematic bias in predictions.

---

## Technologies Used

* Python
* TensorFlow
* Keras
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* Seaborn

---

## Repository Structure

```text
thyao-stock-price-prediction-lstm
│
├── README.md
├── THYAO_LSTM_Stock_Price_Prediction.ipynb
└── THYAO_LSTM_Stock_Price_Prediction_Report.pdf
```

---

## Future Improvements

Possible improvements for future work include:

* Adding technical indicators such as RSI, MACD and Bollinger Bands
* Incorporating macroeconomic variables
* Including exchange rates, interest rates and market indices
* Comparing LSTM with GRU and Transformer architectures
* Performing hyperparameter optimization

---

## Author

**İbrahim Kayar**
Statistics Student
Yıldız Technical University

---

**Note:** This project was developed for educational and research purposes and should not be considered financial investment advice.
