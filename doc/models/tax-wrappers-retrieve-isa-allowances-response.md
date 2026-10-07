
# Tax Wrappers Retrieve Isa Allowances Response

Paginated list of ISA allowances. Contains a `data` array of ISA allowance objects and a `meta` object with offset/limit pagination metadata.

## Structure

`TaxWrappersRetrieveIsaAllowancesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Meta` | [`Meta`](../../doc/models/meta.md) | Required | Offset/limit pagination metadata for a list response. Contains the `offset` and `limit` applied to the request, the `count` of resources returned in this page, and the `total_count` of matching resources. |
| `Data` | [`List<TaxWrappersIsaAllowance>`](../../doc/models/tax-wrappers-isa-allowance.md) | Required | The ISA allowances in this page of results. |

## Example

```csharp
using System.Collections.Generic;
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

TaxWrappersRetrieveIsaAllowancesResponse taxWrappersRetrieveIsaAllowancesResponse = new TaxWrappersRetrieveIsaAllowancesResponse
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
    Data = new List<TaxWrappersIsaAllowance>
    {
        new TaxWrappersIsaAllowance
        {
            Id = new Guid("00001c2a-0000-0000-0000-000000000000"),
            CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            TaxWrapperId = new Guid("0000057e-0000-0000-0000-000000000000"),
            Type = "ANNUAL",
            Status = Status57.Active,
            Currency = "GBP",
            UsedAmount = "used_amount8",
            RemainingAmount = "remaining_amount0",
            ValidFrom = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            TaxYear = "tax_year2",
            ValidTo = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            FirstSubscriptionAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
        },
    },
};
```

