ESB [Enhanced Smart Beta] / Factor Bucket Portfolio Metric Testing Toolkit - v1.0 ReadMe

 -------The code is written on Python v.3.7.0. You will need v.3.7.x to run the code without any problems (in Anaconda pick Jupyter notebook with Python 3 kernel) ---------

_______________________________________________________________________________________________________________________________________________________________________________________________

1. Open the file titled 'FB Portfolio Metric Testing Toolkit.ipynb' by navigating from Jupyter notebook (e.g., V5.7.8 is what we are using) directory structure via Anaconda. 
In case you do not have Anaconda, you can download it from here: https://www.anaconda.com/distribution/
2. You can run each individual cell by hitting the 'Run' button or clicking Shift + Enter.
3. The code currently has the following functionality:
	a. To verify the ESB performance for any given date or range of dates.
	b. To verify the ESB summary performance metrics.
4. User will be asked to pick the ESB first & run all check for the ESB of choice from the list printed at the console. 

Additional information is broken down below.
_______________________________________________________________________________________________________________________________________________________________________________________________

A. Verifying Monthly Returns

The Monthly Return part of the code uses two files as inputs - 'esb_name_positions_returns_5y.xlsx' called "Ret" henceforth and 'stock_returns_19y.xlsm' called "Stock Returns" henceforth. The idea of 
the FB Portfolio Metric Testing Toolkit is to allow users to verify the Factor Bucket Portfolio performances themselves to match it with that being reported by QMIT. The procedure behind this
is as follows: 

	i. Once a date (range) is chosen, the Stock Returns file is used to caluclate portfolio returns for the date by finding the difference between the average of the long ticker returns and short ticker returns. Please note that the entered date should be a last working day of the month.
	ii.This value is then compared with the portfolio return for next date from the Ret file. This was the QMIT reported portfolio return. Both the above values should always turn out the same. Next date is used to source the portfolio returns from the Ret file as the returns in that file were shifted for data storage purposes. 

In case there are instances where the values don't match, kindly contact QuantZ for further clarification.

B. Performance Metric Calculation

The second half of the code calculates a list of metrics for the Factor Bucket portfolio based on the Returns file. 
The 'SPX_returns.csv' file is used to caluclate Beta to S&P.
The metrics covered by the code are:

	i. Annualized Return
	
	ii. Annualized Volatility
	
	iii. Sharpe Ratio
	
	iv. Sortino Ratio
	
	v. Maximum Drawdown
	
	vi. Beta to S&P
