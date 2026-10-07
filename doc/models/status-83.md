
# Status 83

Status of the virtual cash

* ISSUED - Virtual cash decrease is created.
* CONFIRMED - Virtual cash decrease was successfully processed.
* QUEUED - Virtual cash decrease was queued.
* CANCELLED - Virtual cash decrease was cancelled.

## Enumeration

`Status83`

## Fields

| Name |
|  --- |
| `Issued` |
| `Confirmed` |
| `Queued` |
| `Cancelled` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Status83 status83 = Status83.Queued;
```

