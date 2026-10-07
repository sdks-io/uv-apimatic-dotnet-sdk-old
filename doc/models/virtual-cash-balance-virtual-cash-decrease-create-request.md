
# Virtual Cash Balance Virtual Cash Decrease Create Request

Request to decrease an account group's virtual cash balance by a given amount and currency.

## Structure

`VirtualCashBalanceVirtualCashDecreaseCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AccountGroupId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account group. |
| `Amount` | `string` | Required | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Currency` | [`Currency1`](../../doc/models/currency-1.md) | Required | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* EUR — Euro.<br>* GBP — Pound Sterling.<br>* USD — The United States dollar. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

VirtualCashBalanceVirtualCashDecreaseCreateRequest virtualCashBalanceVirtualCashDecreaseCreateRequest = new VirtualCashBalanceVirtualCashDecreaseCreateRequest
{
    AccountGroupId = new Guid("00001b22-0000-0000-0000-000000000000"),
    Amount = "amount8",
    Currency = Currency1.Gbp,
};
```

