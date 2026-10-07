
# Account Valuation List Response

Paginated list of an account's historical end-of-day valuations. Contains a `data` array of account valuation objects and a `meta` object with offset/limit pagination metadata.

## Structure

`AccountValuationListResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Meta` | [`Meta`](../../doc/models/meta.md) | Required | Offset/limit pagination metadata for a list response. Contains the `offset` and `limit` applied to the request, the `count` of resources returned in this page, and the `total_count` of matching resources. |
| `Data` | [`List<AccountValuation>`](../../doc/models/account-valuation.md) | Required | The list of account valuation objects for the current page of results. |

## Example

```csharp
using System.Collections.Generic;
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

AccountValuationListResponse accountValuationListResponse = new AccountValuationListResponse
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
    Data = new List<AccountValuation>
    {
        new AccountValuation
        {
            Id = new Guid("00001c2a-0000-0000-0000-000000000000"),
            CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            AccountId = new Guid("000015ce-0000-0000-0000-000000000000"),
            TotalSecurityValue = new TotalSecurityValue
            {
                Amount = "amount2",
                Currency = Currency.Eur,
            },
            PriceQuality = PriceQuality4.Eod,
            SecurityPositions = new List<AccountValuationSecurityPosition>
            {
                new AccountValuationSecurityPosition
                {
                    Instrument = new Instrument6
                    {
                        Uuid = new Guid("00001fd8-0000-0000-0000-000000000000"),
                        Isin = "isin4",
                    },
                    Quantity = "quantity4",
                    MValue = new MValue
                    {
                        Amount = "amount4",
                        Currency = Currency.Eur,
                        PriceTime = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                            provider: CultureInfo.InvariantCulture,
                            DateTimeStyles.RoundtripKind),
                    },
                    Weight = "weight4",
                    PriceQuality = PriceQuality5.Eod,
                },
            },
            ValuationTime = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
        },
    },
};
```

