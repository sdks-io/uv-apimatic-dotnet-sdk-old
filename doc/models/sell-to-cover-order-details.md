
# Sell to Cover Order Details

A sell-to-cover order placed to raise cash for an outstanding fee amount, together with the amount that remains uncovered after the order settles.

## Structure

`SellToCoverOrderDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid` | Required | The unique identifier of the sell-to-cover order placed to raise cash for a fee amount, as a UUID. |
| `ResidualAmount` | `string` | Required | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

SellToCoverOrderDetails sellToCoverOrderDetails = new SellToCoverOrderDetails
{
    Id = new Guid("00000498-0000-0000-0000-000000000000"),
    ResidualAmount = "residual_amount8",
};
```

