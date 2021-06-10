# Capston-Project--Prediction-of-Close-Price-Nifty50
<p><b>Objective</b> : 
  <li>To perform time series analysis on the NIFTY stock price and forecasting using univariate ARIMA and ARIMAX modeling technique. We further simplified the problem to predict the direction of Close price movements in the next N days (throughout our experiments N can take values 1, 5, and 30).</li> 
  <li>Initially, we will take N=1, that means we want to predict the NIFTY 50 Close price movement in the next day. This is represented as a classification task where there are two possible outcomes (either the index went up in the next day or it went down).</li></p>
  
<p><b>Understanding problem statement</b>:
The Nifty 50 is a stock market index comprised of the shares of 50 of India's most well-diversified firms, covering various economic sectors such as financial services, engineering, pharmaceuticals, and information technology. The weighting of these 50 stocks is determined by their free float market capitalization.This is a time-series activity which we come across in our daily lives.
<p>
<p>Time series means that a series of data points indexed in time order. The following are some of the most frequently asked questions: what will happen with our metrics in the next day/week/month/etc., how many users will instal our app, how much time will they spend online, how many actions will users complete, and so on. We can address these prediction tasks in a variety of ways, depending on the situation.

<p>Depending on the appropriate quality of the prediction, the duration of the forecast period, and, of course, the amount of time we have to select features and tune parameters to achieve desired results, we can approach these prediction tasks in a variety of ways.</p>

<p>Forecasting : The science of forecasting is the art of predicting the future. Businesses can use historical data to consider patterns, make predictions about what will happen and when, and then incorporate the knowledge into their future plans for everything from product demand to marketing.</p>

<p>Many of the areas that naturally generate time series data have forecasting issues. Retail sales, medical research, power planning, sensor network tracking, financial analysis, social activity mining, and database systems are examples of these fields. Forecasting, for example, is critical to automating and optimising operating processes in most industries so that data-driven decisions can be made.</p>

<p>To solve such problem we can have two kinds of approaches
  <li>Time Series Approach</li>
  <li>Machine Learning Approach</li></p>
  
  
 <p><b>Data collection and preparation</b>:</p>
 20 years of data  is collected from NSE website and it consists of four features such as high, low, open and close.

<p>Description of columns in the file:</p>
<li>Date — Date of trade
<li>Open — The open is the starting period of trading on a securities exchange or organized over-the-counter market.
<li>High — Highest price at which a stock traded during the course of the trading day.
<li>Low — Lowest price at which a stock traded during the course of the trading day.
<li>Close — The close is a reference to the end of a trading session in the financial markets when the markets close for the day.
  
 <p>Handling missing values:<p>
<p>Values that are reported as missing may be due to a variety of factors. The absence of a transaction, as well as potential calculation errors, may result in missing values.
Check for how many missing values are there in the data.</p>
<p>There are 35 missing values found in which the entire row is null.We can opt for any of two methods in common.
<li>The first method first is simply to drop the values as the observations with null values are low in number. 
<li>The other method that can be used is to use interpolation. If one opts not to drop this can be used.In which the null value is filled by the average of above and below values. This method can be used here because the values of today and tomorrow are almost in the same range.
  
  
  <p><b>EDA</b>:
 The primary goal of EDA is to support the analysis of data prior to making any conclusions. It may aid in the detection of apparent errors, as well as a deeper understanding of data patterns, the detection of outliers or anomalous events, and the discovery of interesting relationships between variables.
<li>There was a drastic drop in stock prices in the 2007-2009 period.This  can be attributed to the Great Recession that happened during this period.
<li>Also, there is a drop in stock prices in the year 2016. This can be attributed to Demonetisation drive by the central government.
<li>Again ,there is a drastic drop in stock prices in 2020. This is due to the global breakdown amid coronavirus pandemic induced lockdown in India.
<li>By the end of 2020, the stock price started rising.This can be attributed to the lifting of lockdown in the country and across the world.
 
  <p><b>Feature Engineering</b>:
  The features we have are low in number and we don't have that data of the day when we actually want to do prediction. 
  So here comes the importance of feature engineering. Features are created using  the stock  data features based on
   <li>Lag features
   <li>Time  and Features
   <li>Window features such as Rolling and Expanding features using MA and EWMA techniques.
   <li>Volatility
  </p> 
  
  <p><b>Building Time Series Forecasting model</b>:
  The following techniques are used to forecast Close price of NIFTY 50 stock.
   <li>ARIMA using the dependent variable only.
   <li>ARIMAX using the dependent variable and exogenous features and fit the model.
   <li>Facebook Prophet
     
  ARIMA, ARIMAX, and FacebookProphet achieved MAPE of 11%, 8.62% and 8.45% for the three models respectively on the test data.
  </p>
  
  <p><b>Building model using Classifier algorithms:</b>
    Following ensemble techniques were used to predict the directionality of stock Close price for the next day.
    <li>XGBoost
    <li>LGB
      
 Both LGB and XGBoost achieved a recall of 82% on the test data
  </p>
  
  <p><b>Conclusion</b>:
    <li>While using regression models, residuals are quite high.
    <li>Difficult to predict numerical target value using Time Series forecasting models.
    <li>Classification models have a higher chance of predicting the outcome correctly and the result can be interpreted easily.
  </p>
 
  
  
   

  
 


