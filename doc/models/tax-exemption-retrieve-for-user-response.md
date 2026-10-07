
# Tax Exemption Retrieve for User Response

Paginated list of tax exemption orders for an end user. Contains a `data` array of tax exemption objects and a `meta` object with offset/limit pagination metadata.

## Structure

`TaxExemptionRetrieveForUserResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Meta` | [`Meta`](../../doc/models/meta.md) | Required | Offset/limit pagination metadata for a list response. Contains the `offset` and `limit` applied to the request, the `count` of resources returned in this page, and the `total_count` of matching resources. |
| `Data` | [`List<WebhookTaxExemptionCreatedTaxExemption>`](../../doc/models/webhook-tax-exemption-created-tax-exemption.md) | Required | The tax exemption orders in this page of results. |

## Example

```csharp
using System.Collections.Generic;
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

TaxExemptionRetrieveForUserResponse taxExemptionRetrieveForUserResponse = new TaxExemptionRetrieveForUserResponse
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
    Data = new List<WebhookTaxExemptionCreatedTaxExemption>
    {
        new WebhookTaxExemptionCreatedTaxExemption
        {
            Id = new Guid("00001c2a-0000-0000-0000-000000000000"),
            CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            Status = TaxExemptionStatus.Expired,
            UserIds = new List<Guid>
            {
                new Guid("000026a3-0000-0000-0000-000000000000"),
            },
            Country = "country4",
            ValidFromDate = DateTime.Parse("2016-03-13"),
            ValidToDate = DateTime.Parse("2016-03-13"),
            TaxExemptionDetails = new TaxExemptionGermanTaxExemptionDetails
            {
                TaxExemptionType = TaxExemptionType.CivilPartnership,
                TaxExemptionAmount = new TaxExemptionCreateRequestTaxExemptionDetailsAmount
                {
                    Amount = "amount4",
                    Currency = Currency.Eur,
                },
                UtilizedAmount = new TaxExemptionCreateRequestTaxExemptionDetailsAmount
                {
                    Amount = "amount0",
                    Currency = Currency.Eur,
                },
                RemainingAmount = new TaxExemptionCreateRequestTaxExemptionDetailsAmount
                {
                    Amount = "amount8",
                    Currency = Currency.Eur,
                },
            },
        },
    },
};
```

