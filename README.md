# ASX Sector Performance Analysis

This README has been created to define our project scope and overview of the data analysis project. Exploring the problem, questions, datasources and goals. 

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

Our data analysis project has been created to assess the performance of ASX sectors during times of economic turmoil, pandemics and conflicts specifcally. We have encorporated data from both APIs with yfinance and Python libraries to develop a dataframe of historic ASX prices and identify key terms on google. Through this analysis we identify the best performing sectors on the ASX between 2018 and 2023. With this finding a portfolio of the best four sectors is created. The relation between market returns and  terms 'CORONA' and 'UKRAINE' is assessed.

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
2. Open notesbook/project_one_final using jupyter notebook
3. Run the notebook

## Data Collection
To execute the analysis an API from Yfinance was impleneted to return the daily close price of all 11 sectors from the ASX. The data is pulled from the API as a table in daily intervals. For our analysis it is pulled for the timeframe July 2018 to June 2023 and only the 'close' data.  

The pytrends library requires calibration before it can be utilised, first we define the time zone and language we require our analysis to be conducted on. Following this an individual term will be searched for across all geographic regions. The result is a pandas DataFrame which displays the usage of the searched term from 0 to 100 across the assessed period, five years for our analysis.  

## Data Analysis
Explain the data analysis process, including how you assess the data's quality, clean it, and prepare it for analysis.

## Projections
Detail how the Prophet library is used to make projections. Explain how you determine trends and forecast sector performance.

## Contributing
If you welcome contributions, provide guidelines for how others can contribute to your project. Include details about bug reporting, feature suggestions, and pull requests.

## License
Specify the license under which your project is released.

[MIT License](LICENSE)
