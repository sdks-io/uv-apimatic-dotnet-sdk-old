
# Base Amount Scope

The scope of the base amount that fee tiers are evaluated against.

* `GROSS_AMOUNT` — Tiers are evaluated against the gross cash amount of the transaction the fee model is applied to (e.g. the total cash value of an order, a contribution or a transfer).
* `ORDER` — Tiers are evaluated against the total cash value of each order. DEPRECATED: Use `GROSS_AMOUNT` instead. Existing fee models using `ORDER` continue to work unchanged.

## Enumeration

`BaseAmountScope`

## Fields

| Name |
|  --- |
| `GrossAmount` |
| `Order` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

BaseAmountScope baseAmountScope = BaseAmountScope.GrossAmount;
```

