# Stock Price Prediction using LSTM

## Overview

This project predicts the next-day stock closing price using sequential data and an LSTM model.

The goal is to learn patterns from past prices and forecast future values.

---

## Dataset

File: stock_prices.csv

Used column:
- close price

---

## Workflow

### 1. Data Preparation
- Converted date column to datetime
- Sorted data chronologically
- Selected closing price

---

### 2. Normalization
- Used MinMaxScaler
- Scaled values between 0 and 1

---

### 3. Sequence Creation

We use previous 10 days to predict next day.

Example:
Input: Day 1 to Day 10  
Output: Day 11

---

### 4. Train Test Split

Important:
- Used time-based split
- No random split

Reason:
Random split leaks future data into training

---

### 5. Model (LSTM)

Architecture:
- LSTM layer with 50 units
- Dense output layer

---

### 6. Evaluation

Metric used:
- RMSE (Root Mean Squared Error)

Reason:
- Measures prediction error in actual price units

---

### 7. Baseline Comparison

Baseline:
- Average of last 10 days

Purpose:
- Check if LSTM actually learns patterns

---

## Theory

### What is Sequential Data

Data where order matters:
- Stock prices
- Time series

---

### RNN

Recurrent Neural Networks process sequences:
- Use previous information
- Maintain memory

---

### LSTM

Improved RNN:
- Handles long-term dependencies
- Avoids vanishing gradient problem

Uses:
- Memory cells
- Gates (input, forget, output)

---

### Why Not Random Split

Random split causes:
- Future data leakage
- Unrealistic performance

Correct approach:
- Train on past
- Test on future

---

### RMSE

Formula:
Square root of average squared error

Meaning:
- Lower RMSE means better predictions

---

## How to Run

1. Open Google Colab
2. Upload dataset
3. Run all cells

---

## Requirements

pip install pandas numpy matplotlib scikit-learn tensorflow

---

## Key Learnings

- Sequence order is critical
- LSTM captures time dependencies
- Proper split is essential
- Baseline comparison is important
