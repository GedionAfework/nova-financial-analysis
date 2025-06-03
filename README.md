Nova Financial Analysis
A project to analyze financial news sentiment and its correlation with stock market movements using Python, NLP, and technical indicators for Nova Financial Solutions.
Project Overview
This repository implements a three-task project to enhance financial forecasting through data analysis, focusing on seven stocks: AAPL, AMZN, GOOG, META, MSFT, NVDA, and TSLA, using the Financial News and Stock Price Integration Dataset (FNSPID).

Task 1: Set up version control with Git and perform Exploratory Data Analysis (EDA) on financial news data.
Task 2: Conduct quantitative analysis using technical indicators to identify stock trends.
Task 3: Analyze correlations between news sentiment and stock price movements.

Setup Instructions

Clone the Repository:git clone https://github.com/GedionAfework/nova-financial-analysis.git
cd nova-financial-analysis

Create and Activate Virtual Environment:python -m venv venv
venv\Scripts\activate # Windows
source venv/bin/activate # Linux/Mac

Install Dependencies:pip install -r requirements.txt

Required libraries: pandas, textblob, scipy, matplotlib, seaborn, nltk, ta-lib, pynance.
Download NLTK Resources (for Task 3)\*\*:import nltk
nltk.download('vader_lexicon')
nltk.download('punkt')

Data Requirements:
Place raw_analyst_ratings.csv in data/.
Place stock price CSVs (e.g., AAPL_historical_data.csv) in data/yfinance_data/.

Folder Structure
├── data/
│ ├── raw_analyst_ratings.csv # News dataset
│ ├── yfinance_data/ # Stock price CSVs
│ ├── merged_news_stock.csv # Aligned news and stock data
│ ├── news_with_sentiment.csv # News with sentiment scores
│ ├── stock_with_returns.csv # Stock data with daily returns
│ ├── daily_sentiment.csv # Aggregated daily sentiment
│ ├── sentiment_returns.csv # Merged sentiment and returns
│ ├── correlation_results.csv # Correlation coefficients
├── scripts/
│ ├── task_3_date_alignment.py # Task 3: Date alignment
│ ├── task_3_sentiment.py # Task 3: Sentiment analysis
│ ├── task_3_returns.py # Task 3: Daily returns
│ ├── task_3_correlation.py # Task 3: Correlation analysis
│ ├── task_3_visualization.py # Task 3: Scatter plots and heatmap
├── notebooks/
│ ├── eda_analysis.ipynb # Task 1: EDA
│ ├── quantitative.ipynb # Task 2: Technical indicators
| ├── correlation_news_stock.ipynb # Task 3
├── tests/
├── .gitignore
├── requirements.txt

Task 1: Git Setup and Exploratory Data Analysis
Objectives

Set up a Git repository with version control.
Perform EDA on raw_analyst_ratings.csv to understand news data characteristics.

Outputs

Notebook: notebooks/eda_analysis.ipynb
Analyzed headline length statistics, publisher distributions, stock distributions, keyword extraction, and publication time trends.
Visualizations: Bar charts for publishers, histograms for headline lengths, time-series plots for publication frequency.

Data: No additional CSVs generated; used raw_analyst_ratings.csv.

Insights

Identified top publishers and frequent stocks (e.g., AAPL, TSLA).
Highlighted peak publication times, informing data alignment for Task 3.
Keyword analysis revealed common financial terms (e.g., "earnings", "upgrade").

Task 2: Quantitative Analysis with Technical Indicators
Objectives

Compute technical indicators (e.g., moving averages, RSI, MACD) to identify stock trends.
Visualize indicators to support trading decisions.

Outputs

Notebook: notebooks/task_2_quantitative.ipynb
Calculated Simple Moving Average (SMA), Exponential Moving Average (EMA), Relative Strength Index (RSI), and Moving Average Convergence Divergence (MACD) using PyNance and TA-Lib.
Visualizations: Line plots for stock prices with SMAs, RSI overbought/oversold zones, MACD signals.

Data: No additional CSVs; used stock price CSVs in data/yfinance_data/.

Insights

SMA crossovers indicated potential buy/sell signals.
RSI identified overbought (>70) and oversold (<30) conditions.
MACD signals confirmed trend reversals, useful for trading strategies.

Task 3: Correlation between News and Stock Movement
Objectives

Align news and stock price datasets by date.
Perform sentiment analysis on news headlines using TextBlob.
Calculate daily stock returns based on closing prices.
Compute Pearson correlations between daily sentiment scores and stock returns.
Visualize results with scatter plots and a correlation heatmap.

Scripts
Run in a Jupyter Notebook with %matplotlib inline for inline plots:

task_3_date_alignment.py: Normalizes dates, aligns datasets, and saves to merged_news_stock.csv.
task_3_sentiment.py: Assigns sentiment scores to headlines, saves to news_with_sentiment.csv.
task_3_returns.py: Computes daily returns, saves to stock_with_returns.csv.
task_3_correlation.py: Aggregates sentiment, computes correlations, and saves to daily_sentiment.csv and correlation_results.csv.
task_3_visualization.py: Generates scatter plots for each stock and a correlation heatmap, displayed inline.

Outputs

CSVs (in data/):
merged_news_stock.csv: Aligned news and stock data.
news_with_sentiment.csv: News with sentiment scores.
stock_with_returns.csv: Stock data with daily returns.
daily_sentiment.csv: Aggregated daily sentiment scores.
sentiment_returns.csv: Merged sentiment and returns.
correlation_results.csv: Correlation coefficients, p-values, sample sizes.

Visualizations: Inline scatter plots (sentiment vs. returns for each stock) and a correlation heatmap.

Insights

Significant correlations (p < 0.05, |corr| > 0.3) suggest news sentiment may predict stock movements (e.g., AAPL: corr = 0.38, p = 0.02).
Strategy: Buy stocks on high positive sentiment days (>0.5) with high volume.
Limitations: Post-market news may affect next-day returns; TextBlob may miss financial context.

References

TextBlob: https://textblob.readthedocs.io/
NLTK: https://www.nltk.org/
SciPy Pearsonr: https://docs.scipy.org/doc/scipy/reference/generated/scipy.stats.pearsonr.html
Pandas: https://pandas.pydata.org/docs/
Matplotlib: https://matplotlib.org/stable/contents.html
Seaborn: https://seaborn.pydata.org/
TA-Lib: https://ta-lib.github.io/ta-lib-python/
PyNance: https://pynance.net/

Git Workflow

Branches: task-1, task-2, task-3 for respective tasks.
Commits: Descriptive messages (e.g., "Computed correlation analysis for Task 3").
Merge: Merge each task branch into main via Pull Requests after completion.

Notes

Run scripts in a Jupyter Notebook for inline plot display.
Check correlation_results.csv for Task 3 results.
Debug heatmap issues in task_3_visualization.py by inspecting corr_pivot output.
