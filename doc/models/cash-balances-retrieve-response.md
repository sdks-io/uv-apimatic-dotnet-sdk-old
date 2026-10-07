
# Cash Balances Retrieve Response

List of the account group's cash balances.

## Structure

`CashBalancesRetrieveResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Meta` | [`Meta`](../../doc/models/meta.md) | Required | Offset/limit pagination metadata for a list response. Contains the `offset` and `limit` applied to the request, the `count` of resources returned in this page, and the `total_count` of matching resources. |
| `Data` | [`List<Datum>`](../../doc/models/datum.md) | Required | The list of cash balance objects, one per currency the account group holds. |

## Example

```csharp
using System.Collections.Generic;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

CashBalancesRetrieveResponse cashBalancesRetrieveResponse = new CashBalancesRetrieveResponse
{
    Meta = new Meta
    {
        Offset = 222,
        Limit = 126,
        Count = 14,
        TotalCount = 150,
        Sort = "sort4",
        Order = Order1.Asc,
        ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
    },
    Data = new List<Datum>
    {
        new Datum
        {
            AccountGroupId = new Guid("00000794-0000-0000-0000-000000000000"),
            Currency = Currency1.Eur,
            Balance = "balance4",
            LockedForTrading = "locked_for_trading4",
            PendingSettlement = "pending_settlement4",
            AvailableForWithdrawal = "available_for_withdrawal2",
            AvailableForTrading = "available_for_trading8",
        },
    },
};
```

