## Stock Price Prediction Time-Series Analysis
<img src="https://mediacloud.kiplinger.com/image/private/s--x2_BoIgn--/v1604352227/Investing/stock-market-today-110220.jpg" width=700 hieght=500>

### Introduction
One of the most difficult challenges is predicting how the securities exchange will operate. There are numerous variables that influence anticipation, including physical versus psychological causes, rational versus irrational behaviour, and so on.                             
All of these factors combine to make share prices unpredictable and difficult to forecast.   

#### Is it conceivable to leverage AI in this space to our advantage?         
- AI techniques may provide previously unseen examples and insights, which can be utilised to create imprecise predictions based on features such as an organization's most recent statements, quarterly income numbers, and so on.       
- In this study, we'll use publicly available data on an openly documented organization's stock expenses.     
- With LSTM, we'll anticipate this company's future stock price using a combination of AI calculations.     
- The major goal of this essay is to show how these calculations are done. I'll give a fast summary of the process and make crucial connections so you may come back to it later if you need to. If you're new to time management, I recommend starting with the articles listed below.     

### Loading the Data
The Google data is up to 22-05-2020. Let’s take the close column for the stock prediction. We can use the same strategy.
dataset
We should reset the index so that the data will be clear.

- LSTM is very sensitive to the scale of the data, here the scale of the Close value is in a kind of scale, we should always try to transform the value.
- Here we will use min-max scalar to transform the values from 0 to 1.We should reshape so that we can use fit transform.

### Train and Test Split
Whenever training Timeseries data we should divide the data differently we should train the data with the respective date.

Always remember that in time-series data the one data is dependent on other data. The training size should be 65% of the total length of the data frame, the test size should be the difference between the length of the dataset and the training size.

### Data Preprocessing
Now consider the time steps, if I want to predict the price of the stock in a day that how previous data should be considered.

Now the timestep value will be 100. Let’s split the data X, Y. In the 0th iteration the first 100 elements goes as your first record and the 101 elements will be put up in the X. The 100 elements will be put up in the Y.

### LSTM
LSTMs are widely used for sequence prediction problems and have proven to be extremely effective. The reason they work so well is that LSTM can store past important information and forget the information that is not.
LSTM has three gates:
The input gate: The input gate adds information to the cell state,
The forget gate: It removes the information that is no longer required by the model,
The output gate: Output Gate at LSTM selects the information to be shown as output.
 

While Implementing any LSTM, we should always reshape our X train in 3-D, add 1 the reason behind is the time step and the 1 is given to the LSTM.

Here the time step is 100, Whatever the values in train predict and test predict. I got I am just plotting it don’t forget we have to inverse the scaler transform.

### Stock price prediction LSTM prediction
 

- Green indicates the Predicted Data
- Blue indicates the Complete Data
- Orange indicates the Train Data
 
