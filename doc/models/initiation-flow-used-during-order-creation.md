
# Initiation Flow Used during Order Creation

Identifies what triggered the portfolio order.

* API — initiated directly via the client API.
* SAVINGS_PLAN — initiated by a savings plan execution.
* AUTO_INVESTMENT — initiated automatically by auto-investment to invest incoming cash.

## Enumeration

`InitiationFlowUsedDuringOrderCreation`

## Fields

| Name |
|  --- |
| `Api` |
| `SavingsPlan` |
| `AutoInvestment` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

InitiationFlowUsedDuringOrderCreation initiationFlowUsedDuringOrderCreation = InitiationFlowUsedDuringOrderCreation.AutoInvestment;
```

