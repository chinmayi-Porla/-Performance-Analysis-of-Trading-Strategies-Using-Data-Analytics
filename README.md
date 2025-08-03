# Trading-Result-Analysis
### Overview
This project analyzes trading performance data from a CSV file (OrdersReport.csv). It processes trading records, performs data cleaning, and generates statistical insights and visualizations to evaluate trading outcomes over a 28-day period.
#Purpose
#The analysis aims to:

### Clean and preprocess trading data.
Calculate key metrics such as total profit, trade duration, and stop loss/take profit hits.
Simulate and analyze the probability of profit and loss over the next 100 trades.
Provide best-case and worst-case scenario estimates based on simulated data.

### Data
The input data is sourced from OrdersReport.csv, containing trading records with columns:

Ticket: Unique trade identifier
Magic: Trade identifier (modified to replace 12345 with 4444)
Comment: Trade comments (used to identify stop loss/take profit hits)
Open Datetime, Close Datetime: Timestamps for trade open and close
Open Price, Close Price: Prices at trade open and close
Type: Trade type (0 for Buy, 1 for Sell)
Lots: Trade volume
Symbol: Trading instrument (e.g., EURUSD)
Take Profit, Stop Loss: Target levels
Profit, Swap, Commission: Financial outcomes

The analysis derives additional features like trade duration, profit per lot, and stop distance.
### Key Features

### Data Cleaning:
Converts datetime columns to appropriate formats.
Removes unwanted columns (e.g., Ticket, Commission).
Normalizes symbol names by removing "+" and "." characters.
Adjusts profit calculations to include swap and commission.


### Derived Metrics:
Trade duration in minutes.
Profit per lot.
Identification of stop loss and take profit hits.
Stop distance as a percentage.


### Analysis:
Total profit: 118.02 PLN (Polish Złoty).
Trade period: May 19, 2020, to June 16, 2020 (28 days).
Number of trades: 92.
Probability of profit over the next 100 trades: 56.63%.
Best-case scenario (95th percentile): 443.62 PLN.
Worst-case scenario (5th percentile): -306.93 PLN.
Maximum simulated profit: 1305.32 PLN.
Minimum simulated profit: -773.00 PLN.


### Visualizations:
Probability density plot of profit/loss with a highlighted loss region.
Cumulative distribution plot of simulated profits.



### Requirements
The following Python libraries are required:

pandas
numpy
matplotlib
scipy

Install them using:
pip install pandas numpy matplotlib scipy

### Usage

Ensure OrdersReport.csv is available at the specified path (/home/dev/Desktop/OrdersReport.csv).
Run the analysis script to process the data, generate metrics, and create visualizations.
The output includes:
Cleaned dataset details.
Statistical summaries (e.g., total profit, trade count).
Visualizations saved as probability_of_loss.png in the ./img/ directory.



### Output

Cleaned Data: The processed dataset has 92 rows and 24 columns after adding derived features and removing unwanted ones.
Visualizations:
A probability density plot showing the likelihood of loss (saved as ./img/probability_of_loss.png).
A cumulative distribution plot of simulated profits.


### Key Metrics:
Total profit, trade count, and probability of profit/loss.
Best-case and worst-case profit scenarios based on quantiles.



### Notes

The input CSV file must be correctly formatted and accessible.
The currency for profit/loss is PLN (Polish Złoty).
The simulation assumes data in X represents simulated profits for 100 trades (ensure X and X_unity are defined appropriately).
Visualizations use fixed sizes (800x400 pixels for the probability plot, 4x3 inches for the cumulative plot).

