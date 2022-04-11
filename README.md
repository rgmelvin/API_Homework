# API_Homework
Homework for the API unit of FinTech Boot Camp

The main goals of this homework were:

1. Create a personal finance planner
    - Collect crypto prices using the requests Library
    - Collect investments data using Alpaca
    - Perform a savings health analysis
2. Retirement planning analysis
    -Complete a Monte Carlo simulation wiht 500 runs
    -Plot the Monte Carlo simulation.
    -Plot the probability distribution and confidence intervals of the MCMC simulation.
    -Complete the retirement analysis (greater initial investment)
 3. Optional Bonus: Retirement analysis with different proportions of stocks and bonds or greater initial investment.
    -Adjust the portfolio to reflect an early retirement and rerun the analysis to show either a higher stock than bond
    ratio or to have a higher initial investment
    
  The file financial-planner.ipynb contains the required portion of the homework and uses the starter file provided.

  While doing the required portion, especially the Retirement planning part, I felt that the repitition could be most easily handled by a function.
So the Optional Challenge part of the homework is all in a second file: financial-planner-functions.ipynb. I made a new notebook for three reasons:
  First, I wanted to load import matplotlib.pyplot as plt a the beginning so that I could display graphs that were made within the function.
  
  Second, the printing of the MCMC iteration number on the screen takes a great deal of screen real estate and looks messy. I commented out that report   and saved the module as MCForcastTools_2.py.
  
  Last, I wanted to avoid mixing up variables with other parts of the homework.

  I would have liked to also have written a function for retrieving and formatting data from Alpaca. At the time of submission I didn't have it running. There are a couple of issues that I have not worked through quite yet. For example, iterating through a list of tickers to reproduce this:

tickers = ["AGG", "SPY"]

AGG = portfolio_df[portfolio_df['symbol']== 'AGG'].drop('symbol', axis=1)
SPY = portfolio_df[portfolio_df['symbol']== 'SPY'].drop('symbol', axis=1)

I was thinking that I could:

for i in tickers:

  name = ticker[i]
  name = portfolio_df[portfolio_df['symbol']== name].drop('symbol', axis=1)
  
  but I am not sure if that will work or if it will just keep overwriting the variable 'name'. What I want to do is pull the name at ticker[i]
  out and use it to name the dataframe.
  
 
  maybe that would be ok, but, then I get to this:
  
  portfolio_df = pd.concat([AGG, SPY], axis=1, keys=['AGG', 'SPY'])
  portfolio_df.index =portfolio_df.index.date
  
  ... and now I am not sure how to procede. 
  
  There must be a way to iterate and concatenate step by step for any length of ticker list.
  
  I've got a few ideas to try. If those comments are still there, it means that I didn't solve this.
  
