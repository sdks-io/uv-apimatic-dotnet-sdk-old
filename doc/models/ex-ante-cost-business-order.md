
# Ex Ante Cost Business Order

Ex Ante Order details for a business.

*This model accepts additional fields of type object.*

## Structure

`ExAnteCostBusinessOrder`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `BusinessId` | `Guid` | Required | The unique identifier of the business placing the order, as a UUID. |
| `AccountId` | `Guid` | Required | Account ID owning the order. |
| `CashAmount` | `string` | Optional | **Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Required | - |
| `Side` | [`Side8`](../../doc/models/side-8.md) | Required | Whether the order buys or sells the instrument.<br><br>* BUY — The order buys the instrument.<br>* SELL — The order sells the instrument. |
| `InstrumentId` | `string` | Required | International securities identification number defined by [ISO 6166](https://en.wikipedia.org/wiki/International_Securities_Identification_Number).<br><br>**Constraints**: *Pattern*: `^[A-Z]{2}[A-Z0-9]{9}[0-9]$` |
| `InstrumentIdType` | `string` | Required, Constant | The kind of identifier given in `instrument_id`.<br><br>* ISIN — International Securities Identification Number.<br><br>**Value**: `"ISIN"` |
| `OrderType` | [`OrderType4`](../../doc/models/order-type-4.md) | Required | How the order is priced.<br><br>* MARKET — Executes at the best price available.<br>* LIMIT — Executes only at the `limit_price` or better.<br>* STOP — Becomes a market order once the `stop_price` is reached. |
| `Quantity` | `string` | Optional | **Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `LimitPrice` | `string` | Optional | **Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `StopPrice` | `string` | Optional | **Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

ExAnteCostBusinessOrder exAnteCostBusinessOrder = new ExAnteCostBusinessOrder
{
    BusinessId = new Guid("000013e2-0000-0000-0000-000000000000"),
    AccountId = new Guid("000024d8-0000-0000-0000-000000000000"),
    Currency = Currency.Eur,
    Side = Side8.Buy,
    InstrumentId = "instrument_id4",
    InstrumentIdType = "ISIN",
    OrderType = OrderType4.Stop,
    CashAmount = "cash_amount8",
    Quantity = "quantity6",
    LimitPrice = "limit_price6",
    StopPrice = "stop_price4",
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

