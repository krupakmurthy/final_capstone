### Market Mood: Analyzing the Impact of News Sentiment on Stock Movements

**Author**
Nandini Krupa Krishnamurthy

#### Executive summary
This analysis explores the relationship between news sentiment and stock market movements for Dow Jones, NASDAQ, S&P 500, Bitcoin and Dogecoin from October 1, 2024, to February 28, 2025. We performed exploratory data analysis (EDA), sentiment analysis, and machine learning modeling to understand how media coverage influences stock prices and volatility.

#### Rationale
Why should anyone care about this question?

Stock prices don’t move in isolation - they react to news, sentiment, and public perception. Understanding how media sentiment influences the market can help investors, analysts, and policymakers make better decisions. If certain news patterns predict stock movements, traders can use this insight to anticipate market shifts.
For long-term investors, knowing how sentiment affects volatility can help manage risk. And for businesses, this analysis can show how media narratives impact stock value, helping them navigate public relations and market expectations.
In short, news moves markets, and this study helps us understand how

#### Research Question
What are you trying to answer?

Can sentiment analysis of news articles predict stock price changes?

#### Data Sources
What data will you use to answer you question?

To analyze the impact of news sentiment on stock market movements, we used two key datasets for timeframe: October 1, 2024 - January 31, 2025
- Stock Market Data (NASDAQ, Dow Jones, S&P 500, Bitcoin and Dogecoin) YahooFinance: https://pypi.org/project/yfinance/
- News Sentiment Data: GDELT: https://github.com/alex9smith/gdelt-doc-api

#### Methodology
What methods are you using to answer the question?

To understand how news sentiment impacts stock market movements, I followed a structured approach:
- Data Collection & Preprocessing
  - Merged stock market data (NASDAQ, Dow Jones, S&P 500, Bitcoin, and Dogecoin) with news sentiment data from October 2024 to February 2025.
  - Cleaned and formatted the data by handling missing values, converting timestamps, and standardizing columns.

- Feature Engineering
  - Scaled, encoded categorical variables, and created new features for analysis.
  - Applied MinMax Scaling, Standardization, and One-Hot Encoding.
  - Created lagged sentiment features to account for delayed market reactions.

- Exploratory Data Analysis (EDA)
  - Sentiment Distribution: Analyzed whether news was mostly positive, negative, or neutral.
  - Trend Analysis: Visualized sentiment fluctuations over time alongside stock price movements.
  - Volatility Analysis: Examined how sentiment shifts impact stock market volatility and returns.

- Correlation Analysis
  - Built a Random Forest Classifier to predict whether a stock’s price would rise or fall based on:
    - Sentiment Scores
    - News Volume
    - Stock Market Features (e.g., price changes, moving averages)
  - Evaluated model accuracy and feature importance to identify key drivers of market movements.
  
- Modeling
  The following models were implemented to compare performance:
  - Support Vector Classifier (SVC): Since this is effective for classification problems with complex decision boundaries (the dataset has a feature called stock_movement).
  - Random Forest Classifier (RFC): This is robust to overfitting and useful for feature importance analysis.
  - XGBoost: Gradient boosting algorithm that enhances model performance with better regularization.
  - ARIMA: Applied for time series forecasting.

- Why These Models?
  - Each model was selected based on its ability to handle the data structure and improve predictions:
  - mSVC and RFC for classification tasks.
  - XGBoost (without and with lag) for better generalization.
  - ARIMA for time-dependent forecasting.

- Model Evaluation
  - Evaluation Metrics: Accuracy, Mean Squared Error (MSE), Mean Absolute Error (MAE), R² Score.
  - Cross-Validation: K-fold cross-validation is not ideal for predicting stock prices directly because it shuffles data randomly, which breaks the temporal order of stock market data. Since stock prices follow a time-series pattern, future prices depend on past values. k-fold cross validation is not used here. walk-forward CV could be used but the dataset was too small for this.

#### Results
What did your research find?

Results from models:
- Different models performed differently. Of all the models in this notebook - SVC, RFC, XGBoost, XGBoost with lag, ARIMA, XGBoost (both with and without lag) performed the best for the dataset I have, with a R2 score averaging around 0.9 for all stocks.

- Dataset - One key consideration in this analysis is the inclusion of multiple stocks in the dataset. While analyzing a diverse set of stocks can provide a broad perspective, it may introduce noise and inconsistencies. A more focused approach, such as analyzing a single major market mover like NASDAQ, could provide clearer insights into how sentiment impacts stock price movements. By narrowing the scope to a specific index, the model could achieve greater precision in detecting sentiment-driven patterns.

- Feature Importance - Volatility was the strongest predictor, while sentiment score and news volume had a smaller impact, meaning that market conditions drive stock changes more than media sentiment.

- Sentiment Trends - News sentiment fluctuated, but it did not always align directly with stock price changes, indicating that other factors (economic events, earnings reports) may overshadow sentiment effects.

### Key takeaways

- The best model (XGBoost) achieved high R2 score (0.9 on an avg for each stock), suggesting that machine learning can partially predict stock price movements using news sentiment.
- Sentiment alone is not a strong predictor but can be combined with volatility, price trends and financial indicators for better accuracy.
- Time-series forecasting showed limited impact from sentiment, but better feature engineering could improve results.
- Ensemble techniques and deep learning models provide future avenues for improvement

#### Next steps
What suggestions do you have for next steps?

- Dataset enhancement - Get more stock values for a larger timeframe to enhance training
- Enhance Feature Engineering - Include trading volume, earnings reports, and macroeconomic indicators.
- Refine Sentiment Analysis - Test more advanced sentiment models. Use FinBERT or other financial-specific NLP models for better sentiment classification.
- Expand Time-Series Analysis - Combine ARIMA/SARIMAX with machine learning models for hybrid forecasting.
- Include more financial indicators - Including Trading Volume, Moving Averages, Bollinger Bands, Earnings Reports, Central Bank Announcements etc.
- Create better lagged features - Capture delayed market reactions by shifting sentiment scores over multiple time frames (daily, weekly, monthly).


###Conclusion

The project explored predicting stock price movements using news sentiment analysis, applying machine learning (XGBoost, Random Forest, SVC) and time-series (ARIMA) models. Random Forest (68% accuracy) outperformed SVC (49%), showing moderate predictive power. XGBoost achieved the best results with high R² scores (~0.97) for traditional indices, while cryptocurrencies exhibited lower predictability. The XGBoost model with lag features showed mixed results, improving for stable indices but worsening for volatile assets. ARIMA performed the worst, with negative R² scores and high errors, proving ineffective for stock forecasting. Market volatility, not sentiment alone, was a key driver of price changes. The results suggest machine learning models are more reliable, but additional market indicators are needed for better accuracy. Future work should explore hybrid models combining ML and time-series approaches for improved forecasting.

#### Outline of project

- [Link to notebook 1](https://github.com/krupakmurthy/final_capstone/blob/main/capstone.ipynb)


##### Contact and Further Information
