
# Fee Collection Create Request

Request body for creating a fee collection from a fee amount the client has already calculated.

## Structure

`FeeCollectionCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AccountId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account. |
| `Type` | [`Type37`](../../doc/models/type-37.md) | Required | Type of the fee collection.<br><br>* SERVICE_FEE — Service fee intake in a pre-defined cadence, for example monthly.<br>* SERVICE_FEE_LIQUIDATION — Service fee intake resulting from a portfolio liquidation. |
| `CollectionAmount` | `string` | Required | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Required | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* EUR — Euro.<br>* GBP — Pound Sterling. |
| `PeriodStart` | `DateTime` | Required | The start date of the fee collection period, as a [RFC 3339, section 5.6](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) full date in `YYYY-MM-DD` format. |
| `PeriodEnd` | `DateTime` | Required | The end date of the fee collection period, as a [RFC 3339, section 5.6](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6) full date in `YYYY-MM-DD` format. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

FeeCollectionCreateRequest feeCollectionCreateRequest = new FeeCollectionCreateRequest
{
    AccountId = new Guid("000025ea-0000-0000-0000-000000000000"),
    Type = Type37.ServiceFee,
    CollectionAmount = "collection_amount0",
    Currency = Currency.Eur,
    PeriodStart = DateTime.Parse("2016-03-13"),
    PeriodEnd = DateTime.Parse("2016-03-13"),
};
```

