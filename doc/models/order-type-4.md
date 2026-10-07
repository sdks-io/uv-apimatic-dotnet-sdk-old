
# Order Type 4

How the order is priced.

* MARKET — Executes at the best price available.
* LIMIT — Executes only at the `limit_price` or better.
* STOP — Becomes a market order once the `stop_price` is reached.

## Enumeration

`OrderType4`

## Fields

| Name |
|  --- |
| `Market` |
| `Limit` |
| `Stop` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

OrderType4 orderType4 = OrderType4.Market;
```

