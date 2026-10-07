
# Venue

A trading venue at which an instrument is priced, and the price qualities it offers.

*This model accepts additional fields of type object.*

## Structure

`Venue`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Name` | `string` | Optional | The name of the trading venue. |
| `Id` | `Guid` | Required | The unique identifier of the trading venue, as a UUID. |
| `PriceQualities` | [`List<PriceQuality>`](../../doc/models/price-quality.md) | Optional | The available price qualities. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using System.Collections.Generic;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

Venue venue = new Venue
{
    Id = new Guid("00000ac6-0000-0000-0000-000000000000"),
    Name = "name8",
    PriceQualities = new List<PriceQuality>
    {
        PriceQuality.Realtime,
    },
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

