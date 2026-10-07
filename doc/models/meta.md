
# Meta

Offset/limit pagination metadata for a list response. Contains the `offset` and `limit` applied to the request, the `count` of resources returned in this page, and the `total_count` of matching resources.

*This model accepts additional fields of type object.*

## Structure

`Meta`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Offset` | `int` | Required | Amount of resource to offset in the response. |
| `Limit` | `int` | Required | Total limit of the response. |
| `Count` | `int` | Required | Count of the resources returned in the response. |
| `TotalCount` | `int` | Required | Total count of all the resources. |
| `Sort` | `string` | Optional | The field that the list is sorted by. |
| `Order` | [`Order1?`](../../doc/models/order-1.md) | Optional | The ordering applied to the list.<br><br>* ASC — Ascending order.<br>* DESC — Descending order. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

Meta meta = new Meta
{
    Offset = 222,
    Limit = 126,
    Count = 14,
    TotalCount = 150,
    Sort = "sort4",
    Order = Order1.Asc,
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

