🧠 Air Pollution Prediction with RNN Architectures
📌 Project Overview
This project focuses on forecasting PM2.5 air pollution levels using Recurrent Neural Networks (RNNs), including LSTM, GRU, and Bidirectional variants. The goal was to minimize prediction error (MSE) by experimenting with various deep learning architectures and hyperparameters.

🎯 Problem Statement
Accurate prediction of PM2.5 concentration is critical for public health planning. Traditional models often fail to capture temporal dependencies in air quality data. This project leverages RNN-based models to address that gap by learning time-dependent patterns in the data.

🧪 Approach & Methodology
🔍 Data Exploration & Preprocessing
Used hourly PM2.5 readings from the Beijing air quality dataset.

Handled missing values and normalized features using MinMaxScaler.

Created supervised learning sequences using sliding windows.

🤖 Model Architectures
LSTM and GRU networks

Bidirectional RNNs

Stacked and single-layer models

Models with Dropout and regularization

🛠️ Hyperparameter Tuning
Learning rates (0.0007 to 0.01)

Batch sizes (32, 64)

Optimizers: Adam, RMSprop

Units per layer: 32 to 128

Activation functions: relu, tanh

📊 Experiments & Results
Exp	Architecture	Units	Optimizer	LR	Batch	Activation	MSE
1	LSTM(128) → Dropout(0.3) → LSTM(32)	128,32	Adam	0.001	32	relu	5099
4	BiLSTM(128) → Dropout(0.2) → GRU(64)	128,64	RMSprop	0.001	32	relu	4998
5	LSTM(128) → Dropout(0.2) → LSTM(32)	128,32	Adam	0.01	32	tanh	4768
...	...	...	...	...	...	...	...

🧠 Observation: Lower learning rates and use of bidirectional layers improved MSE. Too high learning rates (e.g., 0.01) caused fluctuations. Tanh performed better than ReLU in stacked layers.

📉 Evaluation & Visualizations
Metric used: MSE (Mean Squared Error)

Visual comparison of predicted vs. actual PM2.5 values.

Analysis of overfitting/underfitting by comparing training/validation losses.


⚠️ Challenges Addressed
Vanishing Gradients: Mitigated by using LSTM/GRU cells and tanh activations.

Overfitting: Handled with dropout layers and L2 regularization.

Exploding Gradients: Controlled by gradient clipping and smaller learning rates.

✅ Key Findings
Deeper architectures with regularization performed better.

Bidirectional layers were more effective for capturing complex temporal patterns.

RMSprop slightly outperformed Adam in some GRU models.

🔁 Recommendations for Future Work
Integrate weather data from multiple stations.

Test hybrid models combining CNN and LSTM layers.

Apply attention mechanisms for better sequence weighting.

Try hyperparameter optimization libraries (e.g., Optuna, Ray Tune).

📂 Repository Structure
📦project

 ┣ Air_quality_forecasting_starter_code.ipynb
 ┣ 📄README.md 

 ┣

