
# Status 73

Execution status of the account liquidation order.

* `NEW` — The order has been created and awaits processing.
* `PROCESSING` — The order is being executed.
* `FILLED` — The order has been fully executed.
* `CANCELLED` — The order was cancelled before completion.

## Enumeration

`Status73`

## Fields

| Name |
|  --- |
| `New` |
| `Processing` |
| `Filled` |
| `Cancelled` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Status73 status73 = Status73.Filled;
```

