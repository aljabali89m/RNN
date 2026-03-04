

This project implements a **Time Series Forecasting** model to predict Google's stock price trends. It compares the performance of standard **Recurrent Neural Networks (RNN)** and **Long Short-Term Memory (LSTM)** networks to handle sequential financial data.

---

## 🚀 Getting Started

### 1. Prerequisites
* **Python 3.10+**: Recommended for optimal library support.
* **Jupyter Notebook / Google Colab**: Required to run the `.ipynb` interactive environment.
* **Keras & TensorFlow**: The primary deep learning frameworks used for building the neural networks.

### 2. Installation
* **Clone the Repository**: 
  ```bash
  git clone [https://github.com/aljabali89m/Stock-Price-Prediction.git](https://github.com/aljabali89m/Stock-Price-Prediction.git)
Install Dependencies:Bashpip install numpy pandas matplotlib scikit-learn tensorflow
🧠 Model Comparison: RNN vs. LSTMThe project highlights the architectural differences between two major sequential models:1. Simple RNN (Recurrent Neural Network)Mechanism: Uses a basic feedback loop where the output of the previous step is fed as input to the current step.The Problem: It suffers from Vanishing Gradients. In long sequences (like years of stock data), the model "forgets" information from the beginning of the sequence.2. LSTM (Long Short-Term Memory)Mechanism: An advanced version of RNN that introduces a Cell State and three specific Gates:Forget Gate: Decides what information to discard from the cell state.Input Gate: Decides what new information to store in the cell state.Output Gate: Decides what the next hidden state should be.The Advantage: It maintains a "long-term memory," making it the industry standard for financial forecasting.🛠️ How to Run This ProjectPrepare Data: Ensure Google_Stock_Price_Train.csv and Google_Stock_Price_Test.csv are in the project root.Launch Notebook: Open RNN__LSTM_final.ipynb in your preferred editor.Data Preprocessing:Normalization: Data is scaled using MinMaxScaler to a range of (0, 1).Sliding Window: A window of 60 timesteps is used (predicting $T+1$ based on $T-60$ days).Execution: Run all cells. The model trains for 100 epochs with a Batch Size of 32.Evaluation: The script generates a plot comparing the Real Stock Price vs. Predicted Stock Price.📊 Conclusion & ResultsKey Numbers & FindingsWindow Size: 60 (The model "looks back" 3 months of trading days).Epochs: 100 (Sufficient for the loss curve to stabilize).Performance:Trend Following: Both models capture the general "momentum" effectively.Accuracy: LSTM typically achieves a lower Mean Squared Error (MSE) because it handles the volatility of stock data better than the Simple RNN.Note: While these models are excellent for Technical Analysis, they do not account for "Black Swan" events or sudden news. They are tools for pattern recognition, not guaranteed financial advice.
