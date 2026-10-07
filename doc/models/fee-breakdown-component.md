
# Fee Breakdown Component

A single fee amount contributing to a fee calculation subtotal, identified by the kind of fee it represents.

## Structure

`FeeBreakdownComponent`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | [`Type38`](../../doc/models/type-38.md) | Required | The kind of fee this component represents.<br><br>* TRANSACTION_LUMP_SUM — Lump sum transaction fee.<br>* PLATFORM — Platform fee.<br>* SERVICE — Service fee for a client portfolio.<br>* VAT — Value-added tax. |
| `Amount` | `string` | Required | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

FeeBreakdownComponent feeBreakdownComponent = new FeeBreakdownComponent
{
    Type = Type38.Service,
    Amount = "amount8",
};
```

