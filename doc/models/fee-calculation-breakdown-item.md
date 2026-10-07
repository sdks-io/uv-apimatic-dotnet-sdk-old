
# Fee Calculation Breakdown Item

The fees calculated for one fee model over one subperiod of a fee collection period, broken down into individual components.

## Structure

`FeeCalculationBreakdownItem`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FeeModelId` | `Guid` | Required | The unique identifier of the fee model, as a UUID. Upvest provides this value when a fee model is set up. |
| `SubperiodStart` | `DateTime` | Required | The start date of the fee subperiod, as a [RFC 3339, section 5.6](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) full date in `YYYY-MM-DD` format. |
| `SubperiodEnd` | `DateTime` | Required | The end date of the fee subperiod, as a [RFC 3339, section 5.6](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) full date in `YYYY-MM-DD` format. |
| `SubtotalAmount` | `string` | Required | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Components` | [`List<FeeBreakdownComponent>`](../../doc/models/fee-breakdown-component.md) | Required | Individual fee components contributing to the subtotal. |

## Example

```csharp
using System.Collections.Generic;
using UpvestInvestmentApi.Standard.Models;

FeeCalculationBreakdownItem feeCalculationBreakdownItem = new FeeCalculationBreakdownItem
{
    FeeModelId = new Guid("0000157c-0000-0000-0000-000000000000"),
    SubperiodStart = DateTime.Parse("2016-03-13"),
    SubperiodEnd = DateTime.Parse("2016-03-13"),
    SubtotalAmount = "subtotal_amount6",
    Components = new List<FeeBreakdownComponent>
    {
        new FeeBreakdownComponent
        {
            Type = Type38.TransactionLumpSum,
            Amount = "amount8",
        },
    },
};
```

