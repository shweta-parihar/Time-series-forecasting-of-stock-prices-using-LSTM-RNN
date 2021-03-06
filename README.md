# Time-series-forecasting-of-stock-prices-using-LSTM-RNN

## Introduction
LSTM (Long Short-Term Memory) is a Recurrent Neural Network (RNN) based architecture that is widely used in natural language processing and time series forecasting. It rectifies a huge issue that recurrent neural networks suffer from: short-memory. Using a series of ‘gates’, the LSTM manages to keep, forget or ignore data points based on a probabilistic model. 

## About the problem statement
LSTM methodology, while introduced in the late 90’s, has only recently become a viable and powerful forecasting technique. Classical forecasting methods like ARIMA and HWES are still popular and powerful but they lack the overall generalizability that memory-based models like LSTM offer. I attempt to predict the stock price data based on past stock price data that occurs in time series fashion.

## Methodology
We have used bitcoin minute price data for this problem. There are around 2,300,000 rows in the data available to us. We have several datapoints in the data like Open, High, Low, Close and Volume in a minute timeframe. But we are interested only in the close price for prediction. Also, we can't use the close price directly in our model because the data doesn't have a definite min value and max value. Prices can go as high as possible and potentially to 0 at the lower end. So we calculate the percentage increase/decrease in close price compared to the previous minute's close price, which we further convert to 1 if there is an increase and 0 if there is a decrease.  
  
We essentially convert this to a binary classification problem of whether price will go UP or DOWN, making it standardized and easier for prediction. LSTM models can store memory of previous data to make future predictions. But as sequence length becomes longer, accuracy can be affected depending on the length of sequences the model can handle. I have tested sequence lengths of 60, 120 and 180 for prediction and compared their accuracy to check if changing the sequence length make any difference.
