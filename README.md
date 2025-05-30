# Nova Financial Analysis

A project to analyze financial news sentiment and its correlation with stock market movements using Python, NLP, and technical indicators.

## Setup

1. Clone the repository: `git clone https://github.com/GedionAfework/nova-financial-analysis.git`
2. Create a virtual environment: `python -m venv venv`
3. Activate the virtual environment: `venv\Scripts\activate`
4. Install dependencies: `pip install -r requirements.txt`
5. Place data files in `data/` and `data/yfinance_data/`.

## Folder Structure

- `data/`: Contains `raw_analyst_rating.csv` and `yfinance_data/` with historical stock data.
- `src/`: Source code for reusable modules.
- `notebooks/`: Jupyter notebooks for EDA and analysis.
- `tests/`: Unit tests.
- `scripts/`: Utility scripts.

# Notebooks

- `eda_analysis.ipynb`: Exploratory Data Analysis on raw_analyst_rating.csv, including headline length statistics, publisher and stock distributions, keyword extraction, and publication time analysis.
