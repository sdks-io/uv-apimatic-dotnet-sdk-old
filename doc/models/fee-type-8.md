
# Fee Type 8

What the fee is charged for.

* TRANSACTION_FEE_BUY — A fee charged on a buy order.
* TRANSACTION_FEE_SELL — A fee charged on a sell order.
* ANNUAL_AUM_BASED_FEE — An annual fee charged as a percentage of assets under management.

## Enumeration

`FeeType8`

## Fields

| Name |
|  --- |
| `TransactionFeeBuy` |
| `TransactionFeeSell` |
| `AnnualAumBasedFee` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

FeeType8 feeType8 = FeeType8.TransactionFeeBuy;
```

