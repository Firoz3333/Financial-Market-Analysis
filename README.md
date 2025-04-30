# Financial Sentiment Analysis

This project analyzes the relationship between financial news sentiment and stock price movements for major technology companies (Apple, Meta, Microsoft, NVIDIA, and Tesla). The analysis combines web scraping for news collection, sentiment analysis using NLTK's VADER, and correlation with stock performance data from Yahoo Finance.

## Project Structure

### Data Collection
- Web scraping financial news from The Economic Times and Financial Times
- Company-specific news files saved as CSV files (e.g., `apple_financial_news.csv`, `nvidia_financial_news.csv`)

### Data Processing & Analysis
1. **Phase 1**: Data Aggregation & Cleaning
   - Combines news from different companies
   - Cleans headlines and dates
   - Removes duplicates
   - Outputs: `all_companies_news_raw.csv` and `all_companies_news_cleaned.csv`

2. **Phase 2**: Sentiment Analysis
   - Uses NLTK VADER for sentiment scoring
   - Categorizes headlines as positive, neutral, or negative
   - Generates visualizations of sentiment distribution
   - Output: `all_companies_news_with_sentiment.csv`

3. **Phase 4** (Final): Stock Correlation Analysis
   - Fetches stock price data using yfinance
   - Calculates daily returns and next-day returns
   - Correlates sentiment scores with stock performance
   - Outputs: `merged_sentiment_stock_data_v4.csv` and correlation visualizations

### Visualizations
The project generates several visualizations:
- Sentiment distribution across companies
- Sentiment trends over time
- Correlation heatmaps
- Scatter plots showing sentiment vs. stock returns

## Files Description

### Jupyter Notebooks
- `Financial_Sentiment_Analysis.ipynb`: Main notebook with scraping, cleaning, and sentiment analysis
- `Financial_Analysis_simplified.ipynb`: Analysis of financial data and correlations

### Data Files
- Company-specific news files (`*_financial_news.csv`)
- Combined raw news data (`all_companies_news_raw.csv`)
- Cleaned news data (`all_companies_news_cleaned.csv`)
- News with sentiment scores (`all_companies_news_with_sentiment.csv`)
- Merged sentiment and stock data (`merged_sentiment_stock_data_v4.csv`)

### Visualization Files
- Sentiment distributions (`vader_sentiment_*.png`)
- Correlation heatmaps (`correlation_heatmap_overall.png`)
- Scatter plots for each company (`scatter_sentiment_vs_next_return_*.png`)

## Technologies Used

- **Python Libraries**:
  - **Data Analysis**: pandas, numpy
  - **Web Scraping**: Selenium, BeautifulSoup
  - **Natural Language Processing**: NLTK, VADER sentiment analyzer
  - **Stock Data**: yfinance
  - **Visualization**: Matplotlib, Seaborn
  - **Statistical Analysis**: SciPy

## How to Use This Project

1. **Environment Setup**:
   ```
   pip install pandas numpy matplotlib seaborn nltk selenium bs4 yfinance scipy
   python -c "import nltk; nltk.download('vader_lexicon'); nltk.download('punkt'); nltk.download('stopwords'); nltk.download('wordnet')"
   ```

2. **Running the Analysis**:
   - Execute the notebooks in sequence:
     1. Start with the news scraping sections in `Financial_Sentiment_Analysis.ipynb`
     2. Run the data cleaning and sentiment analysis sections
     3. Run `Financial_Analysis_simplified.ipynb` for stock correlation analysis

3. **Interpreting Results**:
   - Examine the sentiment distribution visualizations to understand news sentiment patterns
   - Review correlation matrices to identify relationships between news sentiment and stock movements
   - Analyze scatter plots to visualize sentiment vs. next-day returns for each company

## Findings

The project investigates whether news sentiment has predictive power for stock price movements. Key findings include:
- Distribution of positive/neutral/negative sentiment across technology companies
- Temporal trends in sentiment scores
- Statistical correlations between sentiment and same-day/next-day stock returns

## Future Improvements

- Incorporate more news sources for broader coverage
- Apply machine learning models for sentiment classification
- Include more advanced features like headline relevance scoring
- Extend analysis to more companies and sectors
- Add trading strategy backtesting based on sentiment signals
