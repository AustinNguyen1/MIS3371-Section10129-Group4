# Short Responsibility Notes #

## Presentation ##
- Immediate Feedback
- Display Confirmation
- Display Current Status
- Required-field Feedback
- Collect Input

## Application Logic ##
- Generate Transaction ID
- Generate Official Status
- Generate Audit Timestamps
- Critical Rule
- Authorization

## Data ##
- Persist Transaction ID
- Persist Official Status
- Persist Audit Timestamps

| Responsibility | Presentation | Application Logic | Data |
|---             |---           |---                |---   |
| **Immediate Feedback** | X |  |  |
| **Display Confirmation** | X |  |  |
| **Display Current Status** | X |  |  |
| **Required-field Feedback** | X |  |  |
| **Collect Input** | X |  |  |
| **Transaction ID** |  | X | X |
| **Official Status** |  | X | X |
| **Audit Timestamps** |  | X | X |
| **Critical Rule** |  | X |  |
| **Authorization** |  | X |  |
