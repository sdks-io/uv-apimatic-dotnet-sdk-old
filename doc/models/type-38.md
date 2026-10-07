
# Type 38

The kind of fee this component represents.

* TRANSACTION_LUMP_SUM — Lump sum transaction fee.
* PLATFORM — Platform fee.
* SERVICE — Service fee for a client portfolio.
* VAT — Value-added tax.

## Enumeration

`Type38`

## Fields

| Name |
|  --- |
| `TransactionLumpSum` |
| `Platform` |
| `Service` |
| `Vat` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Type38 type38 = Type38.Service;
```

