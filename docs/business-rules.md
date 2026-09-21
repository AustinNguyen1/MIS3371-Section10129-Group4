# MarketStreet — Business Rules

## Purpose

These business rules define when a simulated stock trade is allowed, rejected, and recorded in MarketStreet. They are intentionally limited to the main transaction for Milestone 1: **submitting a simulated stock Buy or Sell order**.

## Business Rules

### BR-1 — Valid Trade Type

A transaction must be either a **Buy** order or a **Sell** order. Any other transaction type is invalid and must be rejected.

### BR-2 — Valid Stock Symbol

A trade may only be submitted for a stock symbol recognized by the MarketStreet system. Unsupported or invalid stock symbols must be rejected.

### BR-3 — Valid Share Quantity

The number of shares entered must be a positive whole number greater than zero. Zero, negative, blank, non-numeric, or fractional quantities are not allowed.

### BR-4 — Sufficient Simulated Cash for Buy Orders

A Buy order may only be accepted when the user has enough simulated cash to cover the full value of the transaction.

- If the user has exactly enough simulated cash, the trade is allowed.
- If the user does not have enough simulated cash, the trade is rejected.

### BR-5 — Sufficient Holdings for Sell Orders

A Sell order may only be accepted when the user owns at least the number of shares being sold.

- Selling exactly the number of shares owned is allowed.
- Selling more shares than the user owns is rejected.
- Short selling is not allowed.

### BR-6 — Valid Stock Price Required

A trade cannot be completed unless the system has a valid stock price for the selected stock. If a valid price is unavailable, the transaction must be rejected and no account values may change.

### BR-7 — Accepted Trades Must Update the Simulated Portfolio

When a Buy order is accepted, the user's simulated cash balance decreases and the number of shares owned increases.

When a Sell order is accepted, the number of shares owned decreases and the user's simulated cash balance increases.

### BR-8 — Rejected Trades Must Not Change the Portfolio

If a transaction is rejected, the user's simulated cash balance and stock holdings must remain unchanged. The system should provide a clear reason for the rejection.

If the cash and holdings update fails after a trade has passed validation, the update is rolled back so the user's cash balance and holdings return to their previous values, and the transaction is rejected with a reason.