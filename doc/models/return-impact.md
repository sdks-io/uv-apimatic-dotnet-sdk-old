
# Return Impact

The cumulative effect of the estimated costs on the investment return, shown for each year of the assumed holding period.

*This model accepts additional fields of type object.*

## Structure

`ReturnImpact`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `YearOne` | [`Cost`](../../doc/models/cost.md) | Optional | A cost figure, given both as a cash amount and as a percentage of the amount invested. |
| `YearTwo` | [`Cost`](../../doc/models/cost.md) | Optional | A cost figure, given both as a cash amount and as a percentage of the amount invested. |
| `YearThree` | [`Cost`](../../doc/models/cost.md) | Optional | A cost figure, given both as a cash amount and as a percentage of the amount invested. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

ReturnImpact returnImpact = new ReturnImpact
{
    YearOne = new Cost
    {
        CashAmount = "cash_amount8",
        Currency = Currency.Eur,
        AsPercentage = "as_percentage2",
    },
    YearTwo = new Cost
    {
        CashAmount = "cash_amount0",
        Currency = Currency.Eur,
        AsPercentage = "as_percentage4",
    },
    YearThree = new Cost
    {
        CashAmount = "cash_amount2",
        Currency = Currency.Eur,
        AsPercentage = "as_percentage6",
    },
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

