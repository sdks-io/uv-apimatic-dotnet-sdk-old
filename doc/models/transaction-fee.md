
# Transaction Fee

A fee charged according to a transaction fee model configured with Upvest.

*This model accepts additional fields of type object.*

## Structure

`TransactionFee`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Type` | [`FeeType10`](../../doc/models/fee-type-10.md) | Required | What the transaction fee is charged for.<br><br>* TRANSACTION_FEE_BUY — A fee charged on a buy order.<br>* TRANSACTION_FEE_SELL — A fee charged on a sell order. |
| `TransactionFeeModelId` | `Guid` | Required | The ID of the transaction fee model. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

TransactionFee transactionFee = new TransactionFee
{
    Type = FeeType10.TransactionFeeBuy,
    TransactionFeeModelId = new Guid("00001ff0-0000-0000-0000-000000000000"),
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

