
# Ex Ante Cost Savings Plan Order

Savings Plan Order details.

*This model accepts additional fields of type object.*

## Structure

`ExAnteCostSavingsPlanOrder`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `UserId` | `Guid` | Required | The unique identifier of the end user placing the order, as a UUID. |
| `AccountId` | `Guid` | Required | Account ID owning the order. |
| `CashAmount` | `string` | Required | The cash amount the planned order would invest, as a decimal string.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Required | The currency of the planned order, as an [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) three-letter code. |
| `Side` | [`Side10`](../../doc/models/side-10.md) | Required | Whether the planned order buys or sells the instrument.<br><br>* BUY — The order buys the instrument.<br>* SELL — The order sells the instrument. |
| `InstrumentId` | `string` | Required | International securities identification number defined by [ISO 6166](https://en.wikipedia.org/wiki/International_Securities_Identification_Number).<br><br>**Constraints**: *Pattern*: `^[A-Z]{2}[A-Z0-9]{9}[0-9]$` |
| `InstrumentIdType` | `string` | Required, Constant | The kind of identifier given in `instrument_id`.<br><br>* ISIN — International Securities Identification Number.<br><br>**Value**: `"ISIN"` |
| `OrderType` | [`OrderType6`](../../doc/models/order-type-6.md) | Required | How the planned order is priced.<br><br>* MARKET — Executes at the best price available.<br>* LIMIT — Executes only at the `limit_price` or better.<br>* STOP — Becomes a market order once the `stop_price` is reached. |
| `Period` | [`Period`](../../doc/models/period.md) | Required | The unit of the savings plan interval.<br><br>* WEEK — The interval is counted in weeks.<br>* MONTH — The interval is counted in months.<br>* YEAR — The interval is counted in years. |
| `Interval` | `string` | Required | A whole number of units, as a string of digits.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,63}$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

ExAnteCostSavingsPlanOrder exAnteCostSavingsPlanOrder = new ExAnteCostSavingsPlanOrder
{
    UserId = new Guid("00000e6c-0000-0000-0000-000000000000"),
    AccountId = new Guid("00000100-0000-0000-0000-000000000000"),
    CashAmount = "cash_amount2",
    Currency = Currency.Eur,
    Side = Side10.Buy,
    InstrumentId = "instrument_id8",
    InstrumentIdType = "ISIN",
    OrderType = OrderType6.Stop,
    Period = Period.Year,
    Interval = "interval2",
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

