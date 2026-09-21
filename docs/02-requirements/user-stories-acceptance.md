# User Stories + Acceptance Criteria

## Submit a Buy Order

**As a** user, **I want to** submit a buy order for a stock **so that** I can practice investing without real money.

**Acceptance Criteria:**
Given a valid stock symbol, a positive whole number share quantity, and enough simulated cash to cover the trade, when I submit the order, then the trade is Accepted, my cash balance decreases, my share count increases, and a transaction record is created.

## Submit a Sell Order

**As a** user, **I want to** submit a sell order for shares I own **so that** I can close out a simulated position.

**Acceptance Criteria:**
Given a valid stock symbol and a share quantity no greater than what I currently own, when I submit the order, then the trade is Accepted, my share count decreases, my cash balance increases, and a transaction record is created.

## Rejected Trade — Insufficient Funds or Shares

**As a** user, **I want to** be told clearly why a trade was rejected **so that** I understand what to fix.

**Acceptance Criteria:**
Given a buy order exceeding my available cash or a sell order exceeding my owned shares, when I submit the order, then the trade is Rejected, my balance and holdings remain unchanged, and a specific reason is shown.

## Invalid Input Handling

**As a** user, **I want to** have my input checked before a trade is processed **so that** I don't get a confusing or incorrect result.

**Acceptance Criteria:**
Given a missing or invalid stock symbol, a non-numeric or zero/negative share quantity, or no trade type selected, when I try to submit the order, then the system blocks submission and identifies which field caused the problem.

## View Transaction History

**As a** user, **I want to** see my past trades **so that** I can track how my simulated portfolio has changed over time.

**Acceptance Criteria:**
Given at least one processed trade, when I open my transaction history, then I see each transaction's ID, stock symbol, trade type, quantity, status, and timestamp.