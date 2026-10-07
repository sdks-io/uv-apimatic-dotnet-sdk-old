
# Status 72

Execution status of the account liquidation.

* `NEW` — The liquidation has been created and awaits processing.
* `PROCESSING` — The liquidation orders are being executed.
* `FILLED` — All liquidation orders have been fully executed.
* `CANCELLED` — The liquidation was cancelled before completion.
* `SETTLED` — The liquidation proceeds have settled as cash.

## Enumeration

`Status72`

## Fields

| Name |
|  --- |
| `New` |
| `Processing` |
| `Filled` |
| `Cancelled` |
| `Settled` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Status72 status72 = Status72.Cancelled;
```

