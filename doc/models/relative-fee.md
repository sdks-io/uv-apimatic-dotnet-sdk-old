
# Relative Fee

A fee charged as a rate in basis points on the transaction amount.

*This model accepts additional fields of type object.*

## Structure

`RelativeFee`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | [`FeeType8`](../../doc/models/fee-type-8.md) | Required | What the fee is charged for.<br><br>* TRANSACTION_FEE_BUY — A fee charged on a buy order.<br>* TRANSACTION_FEE_SELL — A fee charged on a sell order.<br>* ANNUAL_AUM_BASED_FEE — An annual fee charged as a percentage of assets under management. |
| `ValueType` | `string` | Required | The type of fee value must be “RELATIVE”.<br><br>**Default**: `"RELATIVE"` |
| `Bps` | `string` | Required | **Constraints**: *Pattern*: `^-?[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

RelativeFee relativeFee = new RelativeFee
{
    Type = FeeType8.AnnualAumBasedFee,
    ValueType = "RELATIVE",
    Bps = "bps2",
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

