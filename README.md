# S&P 500 Index Times Series Analysis

## Repository Contents
This repository contains all of the necessary files and scripts for conducting time series analysis on S&P 500 index stock pricing from January 30th, 2015 to February 21st, 2025. The analysis aims to determine whether different modeling techniques, ARIMA (a model that performs better with linear data) and GARCH (a model that performs better with more volatile data), can truly capture and predict stock market prices after the pandemic that resulted in major industrial changes. 

## 1. Software and Platform

### Programming Languages and Software
- **R**: For data preprocessing, model assumption testing, developing and evaluating the ARIMA and GARCH models

### R Packages
- `tidyverse` – Data cleaning and data filtering
- `dplyr` – Data cleaning and data filtering
- `astsa` – Creating ACF/PACF plots, converting to time series objects, and ARIMA model building
- `fGarch` – Creating GARCH models 
- `kableExtra` – Assistance for table layouts 

### Platform Compatibility
Developed and tested on Mac, but should work on Windows and Linux with appropriate installations.

## 2. Project Folder Structure

```
📂 S&P-500-Times-Series-Analysis  
 ├── 📂 data/  
 ├──── 📂 INITIAL/
 │   │   ├── PerformanceGraphExport.xls 
 ├──── 📂 FINAL/
 │   │   ├── stock_data.csv
 │
 ├── 📂 scripts/  
 │   ├── 01_times_series_analysis.Rmd
 │  
 ├── 📂 output/plots/  
 │   ├── exploratory_plots.jpeg
 │  
 ├── README.md   
```
## 3. Instructions for Reproducing Results

### Stage 1: Data Preparation and Sentiment Analysis in Python
- Download the S&P 500 data set from the S&P 500 websites from January 30th, 2015 to February 21st, 2025
- Extract the csv file and place them in your `data/` directory.
- Open the csv file in Excel and remove both the header and footer that contains unnecessary information.
- Change the column names to date, return from Effective Date and S&P 500 respectively.
- Save the file as stock_data and place it in your `data/` directory.
- Open up RStudio to run `01_times_series_analysis.Rmd`
- You may need to use the following commands in the R console to install the appropriate packages (if you don’t have them already):
  ```r
  install.packages("tidyverse")
  install.packages("dplyr")
  install.packages("astsa")
  install.packages("fGarch")
  install.packages("kableExtra")
  ```
- Import `stock_data.csv` from wherever you have this saved.
- Run the code file to obtain the relevant figures and models. Since we are using the `kableExtra` package, all figures will only appear when you knit your `.Rmd` file. Knitting to HTML has been found to be the easiest way to do this. The following is an outline of the figures:

  - **Times Series Plots** (contains multiple times series plots to determine stationarity)
  - **Differencing** (contains times series plots of differenced data)
  - **ACF + PACF Plots for ARIMA Model Building** (contains the ACF and PACF plot of transformed data for ARIMA model building)
  - ** ARIMA Model Performance** (contains the summarized model performance metrics of the ARIMA models)
  - **ACF + PACF plots + Hypothesis Testing for GARCH Model Building** (contains the ACF and PACF plot of log returns for GARCH model building)
  - ** GARCH Model Performance** (contains the summarized model performance metrics of the GARCH models)
- Annotate any figures using Google Slides
