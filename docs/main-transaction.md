# Main Transaction

## TRANSACTION EVENT
#### User submits a stock trade.

- ### TRIGGER
User wants to buy or sell a stock through MarketStreet.

- ### INPUTS
User ID, number of shares, stock symbol, and buy/sell action.

- ### SYSTEM ACTION
Verify account and available funds/holdings, validate and execute the order using the simulated market price, update the user's portfolio.

- ### OUTCOME
Complete the trade and update the virtual portfolio, or reject the order with a reason.

- ### OFFICIAL RECORD
Transaction ID, user, stock, action, shares, execution price, transaction value, timestamp, and status.

# BREAKDOWN

**User ID:**  
the username of the user

**Number of shares:**  
the amount of shares the user wants to buy/ sell

**Stock symbol:**  
the symbol used to identify a stock

**Buy/sell action:**  
gives the option to either buy or sell the stock based on the user's preference

**Execution price:**  
records the simulated price at which the trade was completed

**Transaction value:**  
records the total simulated value of the trade

**Timestamp:**  
records the time of when the trade happened

**Status:**  
records whether the trade was successfully accepted or rejected
