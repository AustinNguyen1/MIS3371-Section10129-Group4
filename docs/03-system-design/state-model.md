# MarketStreet — State Model (v1)

Four states for a simulated stock trade: **Submitted**, **Validated**, **Accepted**, and **Rejected**. Includes the state transition diagram, state definitions, and allowed transitions.

## State transition diagram

![MarketStreet state transition diagram: Application receives order, Submitted, Validated, Accepted or Rejected; Accepted and Rejected are final.](state-model-v1-diagram.png)

## State definitions

| State | What it means | Entered when | Final? |
|---|---|---|---|
| Submitted | The order was received and saved with a transaction ID. Nothing has been checked yet. | The application receives the order from the user. | No |
| Validated | The order passed every business rule and has a valid price. It is ready to execute. | All checks pass: type, symbol, quantity, price, cash or shares (BR-1 to BR-6). | No |
| Accepted | The trade was executed. Cash and holdings are updated and the record is complete. | The portfolio update commits (BR-7). | Yes |
| Rejected | The trade was not executed. The reason is saved and cash and holdings are unchanged. | Any rule fails, or the portfolio update fails and rolls back (BR-8). | Yes |

Users never set the status themselves. Only the application changes it, and only through the allowed transitions.
