
# Holding Period

The holding period assumed when estimating the costs in this report. Costs are projected on the basis that the instrument is held for this period before being sold.

*This model accepts additional fields of type object.*

## Structure

`HoldingPeriod`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Unit` | [`Unit?`](../../doc/models/unit.md) | Optional | The unit in which the holding period is counted.<br><br>* YEAR — The holding period is counted in years.<br><br>**Default**: `Unit.YEAR` |
| `Quantity` | `int?` | Optional | The number of holding period units assumed, for example 3 for a three-year holding period. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

HoldingPeriod holdingPeriod = new HoldingPeriod
{
    Unit = Unit.Year,
    Quantity = 106,
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

