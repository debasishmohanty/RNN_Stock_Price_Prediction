Project Overview
This project applies advanced Recurrent Neural Networks (RNNs), including LSTM and GRU, to forecast stock trading volumes for multiple tickers (e.g., GOOGL and MSFT). The model leverages sequential dependencies in financial time series data using a sliding window approach.

📂 Dataset
Source: 

Features: Date-wise stock data including volume, open, close, low, high, etc.

Targets: GOOGL_Volume, MSFT_Volume

🧠 Model Architecture
Type: LSTM / GRU (tuned)

Window Size: 63 time steps (1 trading quarter)

Features per Step: 5

Output: 2 real-valued target predictions

🔧 Tunable Hyperparameters:
RNN Units: [32, 64, 128]

Dropout Rate: [0.1, 0.2]

Learning Rate: [0.001, 0.01]

Batch Size: [32, 64]

RNN Type: LSTM or GRU

🧪 Training & Evaluation
Train/Test Split: 80/20 (time-ordered)

Scaling: StandardScaler (input and output)

Loss Function: Mean Squared Error (MSE)

Optimizer: Adam

✅ Final Performance:
Best Model: GRU/LSTM with 64 units, 0.01 LR, 32 batch size

Test MSE: 8.4077

Test MAE: 2.7362

📈 Visual Outputs
Line plots of predicted vs. actual volumes

Training vs. validation loss over epochs

Per-target RMSE for granular evaluation

🚀 How to Run
Clone the repo / download the notebook

Ensure dependencies:

bash
Copy
Edit
pip install numpy pandas matplotlib scikit-learn tensorflow
Run:

python
Copy
Edit
# Preprocess and window data
X_train, y_train, X_test, y_test = prepare_data(...)

# Build and train model
model = build_advanced_rnn_model(...)
model.fit(...)

# Evaluate
model.evaluate(X_test, y_test)
📌 Project Highlights
✅ Sliding window design (63 time steps)

✅ Multi-output regression (2 stocks)

✅ Hyperparameter tuning with grid search

✅ Final test performance and predictions visualization

📁 File Structure
kotlin
Copy
Edit
├── data/
│   └── merged_stock_data.csv
├── notebooks/
│   └── stock_volume_prediction.ipynb
├── models/
│   └── best_rnn_model.h5
├── plots/
│   └── predicted_vs_actual.png
├── README.md
✍️ Author
Debasish Mohanty

[GitHub]
