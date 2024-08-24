LSTM Crypto Price Prediction with Live Tracking and Hyperparameter Tuning

Overview

This project implements a Long Short-Term Memory (LSTM) neural network to predict cryptocurrency prices, specifically focusing on Bitcoin (BTC). The model is enhanced with an attention mechanism and is tuned using Keras Tuner for optimal performance. The project also includes live price prediction with real-time accuracy tracking over a specified duration. Key metrics are recorded and saved for further analysis.

Features

	•	Data Fetching: Historical and live cryptocurrency data is fetched from the CryptoCompare API.
	•	Technical Indicators: The project adds technical indicators like RSI, EMA, Momentum, Bollinger Bands, and MACD to the data to enhance the predictive model.
	•	LSTM with Attention Mechanism: The model is built using LSTM layers with an added attention mechanism to focus on the most relevant parts of the data sequence.
	•	Hyperparameter Tuning: The model’s hyperparameters are optimized using Keras Tuner’s Random Search, with cross-validation to ensure robustness.
	•	Live Price Prediction: The trained model predicts the next price of Bitcoin based on live data, and the accuracy of these predictions is tracked over time.
	•	Real-Time Metrics: Metrics such as current price, predicted price, actual price, and percent difference are recorded and saved to an Excel file.

Installation

To run this project, you need to install the following Python packages:

pip install requests pandas_ta keras keras-tuner

Project Structure

	•	Data Fetching Functions:
	•	fetch_current_price(fsym, tsym): Fetches the current price of a cryptocurrency.
	•	fetch_current_trading_info(fsyms, tsyms): Fetches current trading information for multiple cryptocurrencies.
	•	fetch_historical_crypto_data(fsym, tsym, limit=2000): Fetches historical intraday data with minute intervals.
	•	Data Processing:
	•	add_indicators(data): Adds technical indicators to the historical data.
	•	Modeling:
	•	Attention: Custom Keras layer implementing attention mechanism.
	•	build_model(hp): Builds the LSTM model with attention, using the hyperparameters provided by Keras Tuner.
	•	tune_and_evaluate_model(X, y, n_splits=5): Tunes the model using K-fold cross-validation and evaluates its performance.
	•	Live Prediction:
	•	A loop continuously fetches live BTC prices, makes predictions, compares them with actual prices, and tracks accuracy.

Usage

	1.	Data Preparation: Fetch historical BTC data and add technical indicators.
	2.	Model Training:
	•	Perform hyperparameter tuning using K-fold cross-validation.
	•	Train the final model on the entire dataset using the best parameters found.
	3.	Live Prediction:
	•	Run the live prediction loop for a specified duration.
	•	The loop fetches the current price, predicts the next price, waits for the actual next price, and evaluates prediction accuracy.
	4.	Metrics Output: Metrics from the live prediction are saved to prediction_metrics.xlsx for further analysis.
