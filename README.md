# BitGold 🧠📈

A deep learning project leveraging LSTM (Long Short-Term Memory), a type of Recurrent Neural Network (RNN), to forecast Bitcoin prices using historical data from major financial indicators like gold, oil, S&P 500, and VIX.

---

## 🚀 Overview

BitGold is a multivariate time series forecasting model built using Keras and TensorFlow. It pulls historical data from multiple tickers, calculates technical indicators (such as RSI), and feeds the results into a stacked LSTM model for predicting Bitcoin prices.

---

## 📊 Tickers Used

- **BTC-USD** → Bitcoin
- **GC=F** → Gold Futures  
- **^GSPC** → S&P 500 Index  
- **CL=F** → Crude Oil WTI  
- **^VIX** → Volatility Index (VIX)

---

## ⚙️ Preprocessing

- Merged data from all tickers into a single dataframe  
- Calculated RSI for Bitcoin (14-day window)  
- Removed NaN values  
- Trimmed rows to maintain bi-daily order  

---

## 🧠 Model Architecture

A stacked LSTM architecture was used:

- 2 LSTM layers with 100 units each (ReLU activation)  
- Dense output layer for final prediction  
- Optimizer: Adam  
- Loss: Mean Squared Error  
- Trained for 10,000 epochs with batch size 1024  

---

## 🧪 Training Process

The dataset was split using a custom `split_sequences` function that creates input/output pairs based on a rolling time window.

The model was trained on `trainX` and `trainY`, and evaluated on `testX` and `testY`.

After training:

- Predictions were generated using `model.predict(testX)`  
- Inverse transform applied to scale back to real values  
- RMSE (Root Mean Squared Error) calculated to evaluate performance

---

## 📈 Results

The model's performance was evaluated using RMSE between the predicted and actual Bitcoin prices (after inverse scaling).

---


## 🔧 Tech Stack

- Python  
- Pandas  
- NumPy  
- yfinance  
- ta (technical analysis library)  
- scikit-learn  
- TensorFlow + Keras  

---

## 📌 Future Work

- Integrate news sentiment analysis  
- Try Transformer-based time series models  
- Apply rolling window validation  

---

> “Gold is the past. Bitcoin is the future. BitGold is both.”
