# Data Dictionary

The data dictionary defines the fields used to submit, process, and record a simulated stock trade in MarketStreet.

## Core Transaction Fields

| Field | Business Meaning | Category | Type | Required? | Source | Rule / Constraint | Example |
|---|---|---|---|---|---|---|---|
| transactionId | Unique identifier for one submitted trade | System | string | System | Application | Generated once when the application receives a trade | `TRD-00418` |
| userId | Identifies the user placing the trade | Derived / reference | string | Yes | Account/application | Must identify the account placing the trade | `U10427` |
| stockSymbol | Stock being bought or sold | User | string | Yes | User | Must be a recognized stock symbol | `AAPL` |
| tradeType | Whether the user is buying or selling | User | enum/string | Yes | User | `Buy` or `Sell` only | `Buy` |
| shareQuantity | Number of shares requested | User | integer | Yes | User | Positive whole number | `5` |
| orderType | Type of order selected on the form | User | enum/string | Yes | User | `Market` or `Limit`; current trade workflow covers Market orders only | `Market` |
| limitPrice | Price entered for a Limit order | User | decimal | Conditional | User | Only relevant to Limit orders; not used for execution in the current workflow | `null` |
| executionPrice | Simulated price per share used for an accepted trade | Derived | decimal | If accepted | Application/price source | Must be a valid positive price | `185.50` |
| transactionValue | Total simulated value of an accepted trade | Derived | decimal | If accepted | Application | `shareQuantity × executionPrice` | `927.50` |
| status | Current official trade state | System | enum/string | System | Application | `Submitted`, `Validated`, `Accepted`, or `Rejected` | `Accepted` |
| rejectionReason | Explanation of why a trade was rejected | System | string | If rejected | Application | Required when status is `Rejected` | `Insufficient cash` |
| submittedAt | Time the application received the trade | System / audit | datetime | System | Application | Set when the official trade record is created | `2026-09-20T15:21:08-05:00` |
| validatedAt | Time the trade passed validation | System / audit | datetime | If validated | Application | Set when status becomes `Validated` | `2026-09-20T15:21:09-05:00` |
| completedAt | Time the trade reached a final outcome | System / audit | datetime | If final | Application | Set when status becomes `Accepted` or `Rejected` | `2026-09-20T15:21:10-05:00` |
| updatedAt | Time the official trade record was last updated | System / audit | datetime | System | Application | Updated when the transaction record changes | `2026-09-20T15:21:10-05:00` |

---

## Field Categories

### User-provided data

Entered on the trade form:

- `stockSymbol`
- `tradeType`
- `shareQuantity`
- `orderType`
- `limitPrice` (for the Limit option)

### Derived data

Looked up or calculated by the application:

- `userId`
- `executionPrice`
- `transactionValue`

### System / control data

Created or controlled by the application:

- `transactionId`
- `status`
- `rejectionReason`

### Audit data

Used to identify when important transaction events occurred:

- `submittedAt`
- `validatedAt`
- `completedAt`
- `updatedAt`

---

## Week 4 Form Mapping

Not every field in the data dictionary belongs in the browser form.

### Fields the user can enter

- Stock symbol (`stockSymbol`)
- Buy or Sell (`tradeType`)
- Number of shares (`shareQuantity`)
- Market or Limit (`orderType`)
- Limit price (`limitPrice`, when relevant)

### Fields the application will create or control later

- `transactionId`, `userId`, `status`, and `rejectionReason`
- `executionPrice` and `transactionValue`
- Trusted timestamps (`submittedAt`, `validatedAt`, `completedAt`, `updatedAt`)

The application must enforce the trade rules: sufficient simulated cash for a Buy, sufficient shares for a Sell, and no portfolio changes for a Rejected trade. The current project documents describe immediate execution using a simulated market price; the form has a Limit option, but pending Limit-order behavior is not yet defined.
