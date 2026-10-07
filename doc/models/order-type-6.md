
# Order Type 6

How the planned order is priced.

* MARKET — Executes at the best price available.
* LIMIT — Executes only at the `limit_price` or better.
* STOP — Becomes a market order once the `stop_price` is reached.

## Enumeration

`OrderType6`

## Fields

| Name |
|  --- |
| `Market` |
| `Limit` |
| `Stop` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

OrderType6 orderType6 = OrderType6.Market;
```

