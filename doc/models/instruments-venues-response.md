
# Instruments Venues Response

The trading venues at which price data is available for an instrument.

## Structure

`InstrumentsVenuesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Data` | [`List<Venue>`](../../doc/models/venue.md) | Required | The trading venues available for the instrument. |

## Example

```csharp
using System.Collections.Generic;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

InstrumentsVenuesResponse instrumentsVenuesResponse = new InstrumentsVenuesResponse
{
    Data = new List<Venue>
    {
        new Venue
        {
            Id = new Guid("00001c2a-0000-0000-0000-000000000000"),
            Name = "name0",
            PriceQualities = new List<PriceQuality>
            {
                PriceQuality.Realtime,
            },
            ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
        },
    },
};
```

