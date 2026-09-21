# MarketStreet — Requirements

## Functional Requirements

**FR-1 — Submit a Trade**  
The system shall allow a user to submit a simulated stock trade by choosing a stock symbol, selecting **Buy** or **Sell**, and entering a share quantity.

**FR-2 — Validate Trade Input**  
The system shall verify that the stock symbol, trade type, and share quantity are present and valid before processing the transaction.

**FR-3 — Check Account Eligibility**  
Before accepting a trade, the system shall verify that the user has enough simulated cash for a Buy order or enough shares for a Sell order.

**FR-4 — Create a Transaction Record**  
The system shall create a unique transaction record for each processed trade, including the transaction ID, stock symbol, trade type, quantity, status, and timestamp.

**FR-5 — Return a Clear Trade Result**  
The system shall show whether the trade was **Accepted** or **Rejected**. If rejected, the system shall provide a reason.

**FR-6 — Update and Show Trading Activity**  
When a trade is accepted, the system shall update the user's simulated cash and holdings and make the completed transaction available in transaction history.

---

## Nonfunctional Requirements

**NFR-1 — Accessibility**  
The trade form shall support keyboard navigation and use clear, descriptive labels for inputs, buttons, and trade results.

**NFR-2 — Responsive Design**  
The interface shall remain usable on common laptop and mobile screen sizes without hiding required trade controls or transaction results.

**NFR-3 — Clear Error Feedback**  
Validation messages shall identify the specific input or condition that prevented the trade from being processed.

**NFR-4 — Traceability**  
The system shall preserve transaction IDs, statuses, and timestamps so that submitted trades can be reviewed later.

**NFR-5 — Safe Demonstration Data**  
MarketStreet shall use fictional or non-sensitive demonstration data only and shall not require real brokerage, bank, or payment information.

**NFR-6 — Consistent Interface**  
The application shall use consistent terminology and formatting for Buy/Sell actions, transaction statuses, and validation messages across the trading workflow.

---

## Scope Note

These requirements apply to MarketStreet's Milestone 1 scope: **submitting and processing a simulated stock trade**. Advanced features such as real-money trading, margin, short selling, options, cryptocurrency, and brokerage integration are outside the current scope.
