
# Order 54

The planned order whose costs this report estimates.

*This model accepts additional fields of type object.*

## Structure

`Order54`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `UserId` | `Guid?` | Optional | The unique identifier of the end user placing the order, as a UUID. |
| `AccountId` | `Guid?` | Optional | The ID of the account that owns the order. |
| `CashAmount` | `string` | Optional | The cash amount the planned order would invest, as a decimal string.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Currency` | [`Currency?`](../../doc/models/currency.md) | Optional | The currency of the planned order, as an [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) three-letter code. |
| `Side` | [`Side10?`](../../doc/models/side-10.md) | Optional | Whether the planned order buys or sells the instrument.<br><br>* BUY — The order buys the instrument.<br>* SELL — The order sells the instrument. |
| `InstrumentId` | `string` | Optional | International securities identification number defined by [ISO 6166](https://en.wikipedia.org/wiki/International_Securities_Identification_Number).<br><br>**Constraints**: *Pattern*: `^[A-Z]{2}[A-Z0-9]{9}[0-9]$` |
| `InstrumentIdType` | [`InstrumentIdType?`](../../doc/models/instrument-id-type.md) | Optional | The kind of identifier given in `instrument_id`.<br><br>* ISIN — International Securities Identification Number.<br><br>**Default**: `InstrumentIdType.ISIN` |
| `OrderType` | [`OrderType6?`](../../doc/models/order-type-6.md) | Optional | How the planned order is priced.<br><br>* MARKET — Executes at the best price available.<br>* LIMIT — Executes only at the `limit_price` or better.<br>* STOP — Becomes a market order once the `stop_price` is reached. |
| `Quantity` | `string` | Optional | The number of units the planned order would buy or sell, as a decimal string.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `LimitPrice` | `string` | Optional | The limit price of the planned order, as a decimal string. Applies to `LIMIT` orders.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `StopPrice` | `string` | Optional | The stop price of the planned order, as a decimal string. Applies to `STOP` orders.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `Price` | `string` | Optional | The price used to estimate the costs of the planned order, as a decimal string.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

Order54 order54 = new Order54
{
    UserId = new Guid("0000169e-0000-0000-0000-000000000000"),
    AccountId = new Guid("00000932-0000-0000-0000-000000000000"),
    CashAmount = "cash_amount0",
    Currency = Currency.Eur,
    Side = Side10.Buy,
    InstrumentIdType = InstrumentIdType.Isin,
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

