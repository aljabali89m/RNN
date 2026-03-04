# 📈 Google Stock Price Prediction: RNN vs. LSTM

> A Time Series Forecasting project that compares **Simple RNN** and **LSTM** networks for predicting Google's stock price trends using historical data.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Getting Started](#getting-started)
- [Model Architecture](#model-architecture)
- [How to Run](#how-to-run)
- [Results & Conclusion](#results--conclusion)

---

## 🔍 Overview

This project implements a **Time Series Forecasting** pipeline to predict Google stock prices. It benchmarks two sequential deep learning architectures — **Simple RNN** and **LSTM** — to demonstrate how gating mechanisms solve the vanishing gradient problem in long financial sequences.

---

## 🚀 Getting Started

### Prerequisites

- **Python 3.10+** — Recommended for stability and library compatibility
- **Jupyter Notebook / Google Colab** — To run the `.ipynb` file
- **Keras & TensorFlow** — Core deep learning libraries

### Installation

**1. Clone the repository:**

```bash
git clone https://github.com/aljabali89m/Stock-Price-Prediction.git
cd Stock-Price-Prediction
```

**2. Install dependencies:**

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
```

---

## 🧠 Model Architecture

### 1. Simple RNN (Recurrent Neural Network)

- **Mechanism:** Uses a basic feedback loop where the previous step's output feeds into the current step as input.
- **Limitation — Vanishing Gradients:** On long sequences (e.g., years of stock data), gradients shrink exponentially during backpropagation, causing the model to "forget" early information.

### 2. LSTM (Long Short-Term Memory)

An advanced RNN variant that introduces a **Cell State** and three learnable **Gates**:

| Gate | Function |
|------|----------|
| 🔴 **Forget Gate** | Decides what information to discard from the cell state |
| 🟢 **Input Gate** | Decides what new information to store |
| 🔵 **Output Gate** | Decides what the next hidden state should be |

- **Advantage:** Maintains information across long time horizons, making it the **industry standard** for financial forecasting.

---

## 🛠️ How to Run

### 1. Data Setup

Place the following CSV files in your project root:

```
📁 project/
├── Google_Stock_Price_Train.csv   ← Training data (2012–2016)
├── Google_Stock_Price_Test.csv    ← Test data (2017)
└── RNN__LSTM_final.ipynb
```

### 2. Data Preprocessing

| Step | Detail |
|------|--------|
| **Scaling** | `MinMaxScaler` normalizes prices to range `[0, 1]` |
| **Timesteps** | 60-day lookback window — model uses past 60 days to predict the next price |

### 3. Model Training

Open and run all cells in `RNN__LSTM_final.ipynb`.

**Hyperparameters used:**

| Parameter | Value |
|-----------|-------|
| Layers | 4 (stacked) |
| Units per layer | 50 |
| Dropout rate | 20% |
| Optimizer | Adam |
| Epochs | 100 |
| Batch size | 32 |

---

## 📊 Results & Conclusion

### Technical Summary

- **Trend Following:** Both models successfully capture the general upward/downward momentum of the stock.
- **LSTM Performance:** Typically achieves a lower **Mean Squared Error (MSE)** and produces a smoother, more accurate fit to actual price fluctuations compared to Simple RNN.
- **RNN Limitation:** Struggles with longer dependencies due to vanishing gradients, resulting in noisier predictions.

### Key Takeaway

> The **LSTM** model consistently outperforms **Simple RNN** on this task, validating that gating mechanisms are essential for learning long-range temporal dependencies in financial time series.

---

## 📦 Tech Stack

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-Deep%20Learning-red?logo=keras)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-lightblue?logo=pandas)

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
