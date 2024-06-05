# PREDICTING BITCOIN PRICE TRENDS USING TIME SERIES ANALYSIS.
1. Problem Statement
1.1 Bitcoin's inherent volatility presents a significant challenge for investors and traders seeking to make informed decisions. The difficulty lies in accurately predicting future price trends due to the complex interplay of various factors influencing the market.
1.2 This project aims to tackle this challenge by developing a robust time series analysis model. This model will leverage historical Bitcoin price data to identify patterns and trends. The ultimate goal is to create a predictive tool that provides valuable insights into the future direction of Bitcoin prices. By incorporating these insights, market participants can potentially improve their investment and trading strategies, leading to greater success in the dynamic world of cryptocurrency.
2. Project Goals
2.1 The primary goal of this project is to develop a reliable predictive model utilizing time series analysis techniques. This model will be trained on historical Bitcoin price data to: Identify patterns and trends: By analyzing historical data, the model should uncover recurring patterns and trends in Bitcoin prices. This will allow for a better understanding of the factors influencing price movements.
2.2 Forecast future price movements: Leveraging the identified patterns and trends, the model should be able to generate predictions for future Bitcoin prices. These predictions, while not guarantees, will provide valuable insights for informed decision-making.
2.3 Ultimately, this project aims to equip market participants with a powerful tool to navigate the volatile Bitcoin market. By incorporating the model's forecasts into their strategies, investors and traders can potentially achieve greater success in their cryptocurrency endeavors.
3. Dataset Description
3.1 This project will utilize a publicly available dataset containing historical Bitcoin price data from Kaggle (https://www.kaggle.com/datasets/shiivvvaam/bitcoin-historical-data). The dataset encompasses daily Bitcoin prices from July 18, 2010, to February 9, 2024, providing a comprehensive overview of Bitcoin's price history over nearly 14 years.
3.2 The dataset includes various relevant attributes such as date, opening price, closing price, high price, low price, and trading volume. This rich set of features will serve as the foundation for our time series analysis model.
3.3 By leveraging this comprehensive dataset, the model can be trained to identify patterns and trends within Bitcoin's price history. This in turn will empower the model to generate forecasts for future price movements, aiding market participants in navigating the complexities of the Bitcoin market.
4. Data Cleaning and Analysis
In our project, we adopted a time series analysis approach to develop a model for predicting future Bitcoin price trends. Here's a breakdown of the steps we followed:
4.1 Data Preprocessing:
Data Cleaning: We addressed missing values using appropriate techniques (e.g., mean imputation for numerical features, removal for outliers with low impact). We ensured data type consistency (e.g., converting date strings to datetime format).
Data Standardization: We standardized the numerical features in the dataset (closing price, high price, low price) to have a mean of 0 and a standard deviation of 1. This improved the performance of certain models that are sensitive to feature scales.

5. Stationarity check

Augmented Dickey-Fuller (ADF) Test: We conducted the ADF test on each time series column (Price, Open, High, Low, Vol, Change %). This test helps determine if a time series is stationary, meaning its statistical properties (mean, variance, autocorrelation) remain constant over time.

Transformation for Non-stationary Features:

Since the ADF test indicated non-stationarity in price-related features (Price, Open, High, Low), we applied differencing techniques for price (e.g., differencing the closing price with the previous day's closing price) to achieve stationarity for models like ARIMA. Differencing essentially creates a new series where the statistical properties are constant.

6. Model Selection and Training:

6.1 ACF (Autocorrelation Function) and PACF (Partial Autocorrelation Function): We analyzed the ACF and PACF plots to understand the presence of autocorrelation and identify potential lags for models like ARIMA.

6.2 Random Forest and Gradient Boosting Regressors: We implemented a Random Forest and Gradient Boosting, known for their high accuracy and ability to handle large datasets. Both the model were trained to predict the closing price based on other features (Open, High, Low, Volume). Then we compared which gives better values and accuracy and we proceeded with that.

6.3 ARIMA: Our project leverages a powerful statistical method called ARIMA, or Autoregressive Integrated Moving Average, to forecast future trends in our time series data. By analyzing both the data itself and how past predictions diverged from reality, ARIMA aims to generate highly accurate forecasts. In our case, the software we used determined that an ARIMA(2,1,2) model was the best fit, indicating that the two most recent data points and error terms are most significant for our specific data.

6.4 LSTM: Our project utilized LSTM (Long Short-Term Memory), a cutting-edge deep learning technique, to forecast Bitcoin prices. LSTMs excel at handling sequential data, making them ideal for time series analysis like Bitcoin prices. The evaluation metrics are promising: a high R-squared value (0.993) indicates our model captures a whopping 99.3% of the variance in Bitcoin prices. This translates to an exceptionally strong fit, suggesting the model effectively learns the underlying patterns within the data and offers highly accurate price predictions.

7. Model Estimation

7.1 Based on the differenced ACF and PACF plots, our first attempt to model is the ARIMA model.

7.2 The stepwise search process evaluated several ARIMA models and identified ARIMA(2,1,2) as the model with the lowest AIC (Akaike Information Criterion). AIC is a measure of the goodness-of-fit of a model, where a lower AIC value indicates a better model.

7.3 Therefore, the ARIMA(2,1,2) model is the best model for our time series data out of the models tested by the software program.

8. Conclusion:

Despite the inherent volatility of Bitcoin's market, our study found that traditional statistical approaches, like ARIMA and SARIMA, offer robust predictive capabilities for future price trends. The models effectively captured the dynamic nature of Bitcoin's pricing, providing valuable insights for investors and traders alike. Notably, the LSTM model also performed exceptionally well, capturing 99.3% of the variance in Bitcoin prices. Our findings highlight the importance of leveraging both traditional and modern algorithms for optimal results in cryptocurrency forecasting. The SARIMA model, with its seasonal components, excelled at capturing the complex interplay of market factors, while the LSTM showcased the potential of deep learning in financial predictions. This underscores the potential of integrated time series analysis and cutting-edge neural networks for robust financial forecasts.
