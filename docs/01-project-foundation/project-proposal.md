# Project Proposal

## MarketStreet — Paper Trading System

> MIS 3371 • Reference-based project proposal for the MarketStreet capstone.

## 1. Proposed System

MarketStreet is a web-based **paper trading system** where users can practice buying and selling stocks using simulated money. No real money or securities are traded.

The system focuses on one primary transaction:

> **Simulated Stock Trade**

A transaction starts when a user submits a trade request and ends when the trade is accepted or rejected. An accepted trade updates the user's simulated cash balance and stock holdings.

---

## 2. Business Need

Someone learning to trade may want to practice without risking real money. A paper trading system also needs consistent rules so users can see what happened to each trade.

MarketStreet aims to address these needs:

- Users need a simple way to submit simulated buy and sell orders.
- Orders must be checked for missing or invalid information.
- A user should not be able to buy more stock than their simulated cash allows or sell more shares than they own.
- Cash balances and stock holdings should stay accurate after every accepted trade.
- Users need to know whether a trade was accepted or rejected and why.
- Each trade needs a record that can be reviewed later.

---

## 3. Primary Users / Stakeholders

| Stakeholder | Primary Need |
|---|---|
| Trader / User | Place simulated trades and view their portfolio and trade status |
| Development Team | Build and maintain the interface, trade rules, and data storage |
| System Administrator | Keep the system available and manage technical issues |
| Course Instructor | Review the transaction design and the team's implementation |

---

## 4. Main Transaction

### Transaction name

**Simulated Stock Trade**

### Transaction trigger

A user submits an order to buy or sell a selected stock with a specified number of shares.

### Transaction outcome

The order is either:

- **Accepted:** The simulated trade is completed and the user's cash and holdings are updated; or
- **Rejected:** The trade is not completed, the reason is recorded, and cash and holdings remain unchanged.

### Example transaction

A user with $1,000 in simulated cash submits an order to buy 2 shares of a stock at a simulated execution price of $100 per share. The system checks the order and available cash. If the checks pass and the update succeeds, the system records an accepted $200 trade and updates the user's cash to $800 and holdings by 2 shares.

The team's current state model uses **Submitted → Validated → Accepted**, with a path to **Rejected** if a rule fails or the portfolio update cannot be completed.

---

## 5. Initial Scope

### In scope

- A web form for entering a stock symbol, buy/sell choice, and number of shares
- Validation of required trade details and positive whole-share quantities
- A simulated execution price and trade-value calculation
- Checks for enough simulated cash to buy or enough shares to sell
- Application-controlled transaction states: Submitted, Validated, Accepted, and Rejected
- A unique transaction ID and important timestamps
- Updating simulated cash and stock holdings for accepted trades
- Recording accepted and rejected transactions and displaying the result to the user
- Storing official trade and portfolio records in a database as the application is developed

### Out of scope for the initial documented transaction

- Trading with real money or placing orders on a real exchange
- Real brokerage or bank account connections
- Real deposits and withdrawals
- Live execution on an actual stock market
- **Pending limit-order processing:** The current four-state workflow covers immediate simulated execution. A limit-order feature would need its own rules and an additional state for orders waiting to execute before it is supported.

---

## 6. Success Criteria

MarketStreet succeeds as a course project when it demonstrates that a simulated stock trade can be:

1. entered through a usable web form;
2. checked for valid input and enough cash or shares;
3. given a unique transaction ID and a controlled status;
4. executed at a defined simulated price, or rejected with a clear reason;
5. reflected correctly in the user's cash balance and stock holdings if accepted;
6. saved as an official transaction record;
7. displayed to the user with its outcome; and
8. reviewed later using its transaction details, timestamps, and history.

These capabilities will be developed and documented as the course project progresses.
