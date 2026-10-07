
# Status 53

Status of the fee collection.

* PROCESSING — The fee collection is in progress.
* FINALISED — The fees have been collected from the account and the funds transferred to the client.
* CANCELLED — The fee collection was cancelled.

## Enumeration

`Status53`

## Fields

| Name |
|  --- |
| `Processing` |
| `Finalised` |
| `Cancelled` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Status53 status53 = Status53.Processing;
```

