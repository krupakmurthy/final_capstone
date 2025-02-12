### Market Mood: Analyzing the Impact of News Sentiment on Stock Movements

**Author**
Nandini Krupa Krishnamurthy

#### Executive summary
This analysis explores the relationship between news sentiment and stock market movements for Dow Jones, NASDAQ, and S&P 500 from October 1, 2024, to January 31, 2025. We performed exploratory data analysis (EDA), sentiment analysis, and machine learning modeling to understand how media coverage influences stock prices and volatility.

#### Rationale
Why should anyone care about this question?

Stock prices don’t move in isolation—they react to news, sentiment, and public perception. Understanding how media sentiment influences the market can help investors, analysts, and policymakers make better decisions. If certain news patterns predict stock movements, traders can use this insight to anticipate market shifts.
For long-term investors, knowing how sentiment affects volatility can help manage risk. And for businesses, this analysis can show how media narratives impact stock value, helping them navigate public relations and market expectations.
In short, news moves markets, and this study helps us understand how

#### Research Question
What are you trying to answer?

Can sentiment analysis of news articles predict stock price changes?

#### Data Sources
What data will you use to answer you question?

To analyze the impact of news sentiment on stock market movements, we used two key datasets for timeframe: October 1, 2024 - January 31, 2025
- Stock Market Data (NASDAQ, Dow Jones, S&P 500) YahooFinance: https://pypi.org/project/yfinance/
- News Sentiment Data: GDELT: https://github.com/alex9smith/gdelt-doc-api

#### Methodology
What methods are you using to answer the question?

To understand how news sentiment impacts stock market movements, I followed a structured approach
- Data Collection & Preprocessing
  - Merged stock market data (NASDAQ, Dow Jones, S&P 500) with news sentiment data from October 2024 to January 2025.
  - Cleaned and formatted the data (handled missing values, converted timestamps, standardized columns).

- Exploratory Data Analysis (EDA)
  - Sentiment Distribution: Checked whether news was mostly positive, negative, or neutral.
  - Trend Analysis: Visualized sentiment fluctuations over time alongside stock price movements.
  - Volatility Analysis: Examined how sentiment shifts impact stock market volatility and returns.

- Correlation Analysis
  - Built a Random Forest Classifier to predict whether a stock’s price would rise or fall based on:
    - Sentiment Scores
    - News Volume
    - Stock Market Features
  - Evaluated model accuracy and feature importance to identify key drivers.

#### Results
What did your research find?
Results from the baseline model:
- Model Accuracy - The baseline model achieved 51% accuracy, which is only slightly better than random guessing, suggesting that news sentiment alone is not enough to predict stock price direction.

- Feature Importance - Volatility was the strongest predictor, while sentiment score and news volume had a smaller impact, meaning that market conditions drive stock changes more than media sentiment.

- Sentiment Trends - News sentiment fluctuated, but it did not always align directly with stock price changes, indicating that other factors (economic events, earnings reports) may overshadow sentiment effects.

#### Next steps
What suggestions do you have for next steps?
- Enhance Feature Engineering
- Refine Sentiment Analysis
- Test Different Time Lags
- Try More Advanced ML Models

#### Outline of project

- [Link to notebook 1](https://github.com/krupakmurthy/final_capstone/blob/main/capstone.ipynb)


##### Contact and Further Information
