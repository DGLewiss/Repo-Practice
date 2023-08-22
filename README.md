# ASX Sector Performance Analysis

Analyze the performance of ASX sectors during periods of volatility over the last five years. This project aims to provide investment insights on how different sectors perform during times of global pandemic, conflicts, and periods of low volatility.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Data Collection](#data-collection)
- [Data Analysis](#data-analysis)
- [Projections](#projections)
- [Contributing](#contributing)
- [License](#license)

## Introduction
This project focuses on studying the performance of ASX sectors in response to macroeconomic events such as global pandemics and conflicts, compared to periods of lower volatility. The end goal is to provide investment advice and insights to help investment advisors make informed decisions.

## Features
- Collect historical data on ASX sector performance using APIs.
- Analyze and clean the collected data to ensure accuracy.
- Correlation analysis to determine the impact of economic surges on sectors.
- Volatility Analysis to discover risk of sectors. 
- Utilize sentiment analysis to gauge market sentiment during various events.
- Use the Prophet library to make projections for sector performance.
- Visualize and present findings to highlight sector performance variations.

# Installation - Pytrends

This guideline is created to provide support with the installation of new packages and/ or files required to utilise the Project 1 code. 

## Requirements
* Python version 3.3+ 
* Requires Requests, lxml, Pandas

—

## Install 
 * Open a new terminal window
	‘’’shell 
	pip install pytrends
	‘’’
* Connect to Google	
	‘’’’shell
	from pytrends.request import TrendReq
	pytrends = TrendReq(hl = ‘en-US’, tz=360)
	‘’’
—
 # Installation - Prophet

Propet is on PyPI so you can use pip to install 
```shell 
Python -m pip install prophet
```

## Usage
Explain how to use the project:

1. Collect data using APIs: `python data_collection.py`
2. Analyze and clean data: `python data_analysis.py`
3. Perform sentiment analysis: `python sentiment_analysis.py`
4. Make projections using Prophet: `python projections.py`
5. Visualize results: `python visualize_results.py`

## Data Collection
Describe how data is collected from APIs (in your case, yfinance). Explain the data fields you're collecting and any potential challenges or considerations.

## Data Analysis
Explain the data analysis process, including how you assess the data's quality, clean it, and prepare it for analysis.

## Projections
Detail how the Prophet library is used to make projections. Explain how you determine trends and forecast sector performance.

## Contributing
If you welcome contributions, provide guidelines for how others can contribute to your project. Include details about bug reporting, feature suggestions, and pull requests.

## License
Specify the license under which your project is released.

[MIT License](LICENSE)
