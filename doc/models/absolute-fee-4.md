
# Absolute Fee 4

A fee charged as a fixed cash amount.

*This model accepts additional fields of type object.*

## Structure

`AbsoluteFee4`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | [`FeeType8`](../../doc/models/fee-type-8.md) | Required | What the fee is charged for.<br><br>* TRANSACTION_FEE_BUY — A fee charged on a buy order.<br>* TRANSACTION_FEE_SELL — A fee charged on a sell order.<br>* ANNUAL_AUM_BASED_FEE — An annual fee charged as a percentage of assets under management. |
| `ValueType` | `string` | Required | The type of fee value must be “ABSOLUTE”.<br><br>**Default**: `"ABSOLUTE"` |
| `CashAmount` | `string` | Required | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Required | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* EUR — Euro.<br>* GBP — Pound Sterling. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

AbsoluteFee4 absoluteFee4 = new AbsoluteFee4
{
    Type = FeeType8.TransactionFeeBuy,
    ValueType = "ABSOLUTE",
    CashAmount = "cash_amount8",
    Currency = Currency.Eur,
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

