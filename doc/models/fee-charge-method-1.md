
# Fee Charge Method 1

Indicates how the transaction fee is charged.

* `CHARGED_BY_CLIENT` — The fee is charged by the client as part of post-trade settlement; the fee movement occurs outside Upvest cash balances.
* `COLLECTED_BY_UPVEST` — The fee is charged by the client and collected by Upvest; the fee amount is debited from the user's Upvest cash balance.

## Enumeration

`FeeChargeMethod1`

## Fields

| Name |
|  --- |
| `ChargedByClient` |
| `CollectedByUpvest` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

FeeChargeMethod1 feeChargeMethod1 = FeeChargeMethod1.ChargedByClient;
```

