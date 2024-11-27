My project on safer, lower risk, and accurate Stock Price Prediction Algorithm which makes use of given technologies:
1. LSTMs (Recurrent Neural Networks)
2. Technical Indicators
3. Sentiment Analysis
4. Validation by each of the above techniques to decide buy/sell order.

# How it works

This model searches for the financial data of the given Financial Symbol/Instrument from the yfinance (Yahoo Finance) api for a given time period and imports it as a dataframe and cleans it. Some Financial Indicators are calculated on this data and stored to use them for validation later. Then, the imported data is fed to a LSTM, which learns the underlying patterns in the data to be able to predict the Instrument prices for  the upcoming 30 days.
Next, this model then fetches news related to the given Financial Instrument from Yahoo Finance ("https://finance.yahoo.com/"), then uses this data to analyse the market sentiment of the concerned Financial Instrument using Sentiment Analysis. I've used a model called Distilled Roberta from "huggingface.co" to whose url I'll attach in the end.

The final prediction of this project/bot relies on the voting system (validation) by each of the above mentioned processes (Technical Indicators, Neural Networks, Sentiment Analysis) which will each provide with a confidence metric(float) which defines whether the current signal for the given Financial Instrument is positive, negative or neutral.

Lastly, I've backtested this algorithm to compare the results with other trading techniques (buy and hold, just technical indicators, just Neural Networks), and transformed this comparison into a more organised and readable chart/graph.

Currently, the hyperparameters of the LSTM are tuned for the particular instrument, AAPL (Apple), and there is no option to tune the hyperparameters for other instruments except manual search. But other indicators work fine including Technical Indicators and Market analysis.

# Resources used in this project:

1. Sentiment Analysis: DistilRoberta-financial-sentiment | "https://huggingface.co/mrm8488/distilroberta-finetuned-financial-news-sentiment-analysis"

2. Libraries used:
   yfinance, transformers, feedparser (required to installed first in a google colab notebook from pip)
   numpy, pandas, tensorflow, keras, matplotlib, sklearn
