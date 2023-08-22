# ASX Sector Performance Analysis

This README has been created to define our project scope and overview of the data analysis project. Exploring the problem, questions, data sources and goals. 

___
## Presentation access:
https://docs.google.com/presentation/d/1AkKurQ7TPZQDz8eB-bfLGw0by08MCgJ46-jiAprKpc4
___
## Table of Contents
- [Introduction](#introduction)
- [Installation](#installation)
- [Usage](#usage)
- [Data Collection](#data-collection)
- [Data Analysis](#data-analysis)
- [Projections](#projections)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Our data analysis project has been created to assess the performance of ASX sectors during times of economic turmoil, pandemics and conflicts specifically. We have incorporated data from both APIs with yfinance and Python libraries to develop a dataframe of historic ASX prices and identify key terms on Google. Through this analysis, we identify the best-performing sectors on the ASX between 2018 and 2023. With this finding a portfolio of the best four sectors is created. The relation between market returns and the terms 'CORONA' and 'UKRAINE' is assessed.

___
# Installation 
### Installation - Pytrends

This guideline is created to provide support with the installation of new packages and/ or files required to utilise the Project 1 code. 

### Requirements
* Python version 3.3+ 
* Requires Requests, lxml, Pandas

### Install 
 * Open a new terminal window
	```shell 
	pip install pytrends
	```
* Connect to Google	
    ```shell
	from pytrends.request import TrendReq
	```
	```
	pytrends = TrendReq(hl = ‘en-US’, tz=360)
	```
	
### Installation - Prophet

Propet is on PyPI so you can use pip to install 
```shell 
Python -m pip install prophet
```
___
## Usage

1. Complete the Installation instructions
2. Open notebook/project_one_final using jupyter notebook
3. Run the notebook

## Data Collection
To execute the analysis an API from Yfinance was implemented to return the daily close price of all 11 sectors from the ASX. The data is pulled from the API as a table at daily intervals. For our analysis it is pulled for the timeframe July 2018 to June 2023 and only the 'close' data.  

The Pytrends library requires calibration before it can be utilised, first, we define the time zone and language we require our analysis to be conducted. Following this, an individual term will be searched for across all geographic regions. The result is a pandas DataFrame which displays the usage of the searched term from 0 to 100 across the assessed period, five years for our analysis.  

## Data Analysis
###### Importing Libraries
The notebook begins by importing the required libraries to complete the analysis. Libraries include data manipulation packages such as pandas and visualisation packages such as matplotlib. New packages in this model are Prophet and pytrends which are specialised packages for modelling and sentiment analysis. 

###### Defining Sectors and Date Range
A dictionary is defined as 'sectors' and each sector name is the key with corresponding ticker symbols as values. The date range is defined as 'start_date' and 'end_date' which has five years in between.

###### Downloading Financial Date
The scripts will download financial data for the defined sectors. This is completed through the yfinance library. The data is downloaded for the defined period of five years and stored in the 'data' DataFrame.

###### Extracting Close data
The 'Close' prices for all tickets are pulled from downloaded data in the 'close_data' DataFrame.

###### Calculating Returns
Daily returns are calculated by applying the percentage change into the 'Close' prices column using the 'pct_change()' function. A cumulative product of (1 + daily returns) is calculated to simulate the portfolio's performance, and the final values are sorted.

###### Portfolio Selection and Weights
The top-performing sectors are allocated to an investment portfolio, and the initial investment value and weights are assigned to each sector.

###### Cleaning the Data
Null values in the daily returns DataFrame is dropped using the .dropna() method to create the 'final_returns_df'.

###### Data Preparation for Prophet
The final returns DataFrame is used to calculate the portfolio's cumulative returns and input into the Prophet forecasting model. Reset the DataFrames index and column names are adjusted to meet the requirements of Prophet.

###### Resampling Data 
The portfolio returns are resampled to weekly frequency so it is compatible with the sentiment analysis

###### Identifying Shocks (Events)
Dates of significance that had been pre-identified have been created into a DataFrame for the Prophet model.

###### Prophet Model
The Prophet model is initialized with the identified events as holidays. The model is fitted to the historical portfolio returns data.

###### Generating Forecasts
The Prophet model is used to generate forecasts for a future time period.

###### Sentiment Analysis with pytrends
The pytrends library is utilised to assess the online search interest in key terms "CORONA" and "UKRAINE"

###### Handling Sentiment Data
Any data that contained a '0' has been converted to a '1' to eliminate division by zero errors. 

###### Calculating Sentiment Change
Percentage Change of the Sentiment data is calculated with the '.pct_change()' function.

###### Combining the Sentiment and Portfolio data
the sentiment and portfolio data is combined into one DataFrame in preparation for correlation analysis. This has to be completed to analyse the correlation of market returns and key-term interest. 

###### Correlation Calculations
The correlation between sentiment changes and market returns is calculated using the .corr() method.

## Projections
The prophet library is incorporated to extrapolate market closes from the custom portfolio of the best-performing ASX Sectors. The Prophet library completes time series forecasting by identifying trends, seasonality and modelling. By preparing the sectors into a single returns DataFrame we can capitalise on the seasonality components pre-incorporated into the prophet model. Future insights are generated from the model, providing insight into the anticipated performance of the portfolio. Within the plot we extrapolate one year into the future with a shock occurring on 11/03/2020 to represent the CORONA pandemic announcement Additionally, another shock was incorporated on 24/02/2022 for the invasion of Russian forces into Ukraine. 

## Contributing
If you welcome contributions, provide guidelines for how others can contribute to your project. Include details about bug reporting, feature suggestions, and pull requests.

## License
Specify the license under which your project is released.

[MIT License](LICENSE)
