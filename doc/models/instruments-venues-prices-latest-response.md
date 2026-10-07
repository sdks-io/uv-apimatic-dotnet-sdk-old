
# Instruments Venues Prices Latest Response

The latest available price data for an instrument at a venue, comprising the current bids, asks, and last trade.

## Structure

`InstrumentsVenuesPricesLatestResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `PriceQuality` | [`PriceQuality2`](../../doc/models/price-quality-2.md) | Required | The quality of the price data returned.<br><br>* REALTIME — Priced in real time.<br>* DELAYED — Priced with a delay set by the data owner. |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Required | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* EUR — Euro.<br>* GBP — Pound Sterling. |
| `Bids` | [`List<Bid>`](../../doc/models/bid.md) | Optional | Bids for the instrument. |
| `Asks` | [`List<Ask>`](../../doc/models/ask.md) | Optional | Asks for the instrument. |
| `LastTrade` | [`LastTrade`](../../doc/models/last-trade.md) | Optional | A single trade in an instrument, with the price and size at which it executed. |

## Example

```csharp
using System.Collections.Generic;
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

InstrumentsVenuesPricesLatestResponse instrumentsVenuesPricesLatestResponse = new InstrumentsVenuesPricesLatestResponse
{
    PriceQuality = PriceQuality2.Realtime,
    Currency = Currency.Eur,
    Bids = new List<Bid>
    {
        new Bid
        {
            Time = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            Price = "price8",
            Size = "size6",
            ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
        },
    },
    Asks = new List<Ask>
    {
        new Ask
        {
            Time = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            Price = "price2",
            Size = "size4",
            ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
        },
        new Ask
        {
            Time = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            Price = "price2",
            Size = "size4",
            ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
        },
        new Ask
        {
            Time = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
                provider: CultureInfo.InvariantCulture,
                DateTimeStyles.RoundtripKind),
            Price = "price2",
            Size = "size4",
            ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
        },
    },
    LastTrade = new LastTrade
    {
        Time = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
            provider: CultureInfo.InvariantCulture,
            DateTimeStyles.RoundtripKind),
        Price = "price4",
        Size = "size2",
        ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
    },
};
```

