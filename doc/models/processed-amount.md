
# Processed Amount

How much of the fee amount has been covered so far, split by the source of the cash, together with any amount still outstanding.

*This model accepts additional fields of type object.*

## Structure

`ProcessedAmount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `CashBalance` | `string` | Optional | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `SellToCover` | `string` | Optional | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `TotalResidualAmount` | `string` | Optional | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

ProcessedAmount processedAmount = new ProcessedAmount
{
    CashBalance = "cash_balance2",
    SellToCover = "sell_to_cover4",
    TotalResidualAmount = "total_residual_amount4",
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

