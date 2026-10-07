
# Account Liquidation

Represents an account liquidation — a request to sell all investment positions in an account and convert the proceeds to cash. Contains references to each individual sell order.

## Structure

`AccountLiquidation`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid` | Required | Universally Unique Identifier (UUID) of an account liquidation. |
| `CreatedAt` | `DateTime` | Required | Date and time when the resource was created. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `UpdatedAt` | `DateTime` | Required | Date and time when the resource was last updated. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `UserId` | `Guid?` | Optional | ID of the user who owns the account. Exactly one of user_id or business_id will be set; the other will be null. |
| `BusinessId` | `Guid?` | Optional | ID of the business that owns the account. Exactly one of user_id or business_id will be set; the other will be null. |
| `AccountId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account. |
| `CashAmount` | `string` | Required | A positive decimal amount, as a string.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `Currency` | [`Currency173`](../../doc/models/currency-173.md) | Required | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* `EUR` — Euro.<br>* `GBP` — Pound sterling. |
| `Status` | [`Status72`](../../doc/models/status-72.md) | Required | Execution status of the account liquidation.<br><br>* `NEW` — The liquidation has been created and awaits processing.<br>* `PROCESSING` — The liquidation orders are being executed.<br>* `FILLED` — All liquidation orders have been fully executed.<br>* `CANCELLED` — The liquidation was cancelled before completion.<br>* `SETTLED` — The liquidation proceeds have settled as cash. |
| `Orders` | [`List<AccountLiquidation1>`](../../doc/models/account-liquidation-1.md) | Required | The individual position sell orders that make up this account liquidation. |
| `FeeCollectionId` | `Guid?` | Required | Identifier of the fee collection associated with this liquidation. Null when no fee applies. See the Fees API to retrieve fee details. |

## Example

```csharp
using System.Collections.Generic;
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;

AccountLiquidation accountLiquidation = new AccountLiquidation
{
    Id = new Guid("00000070-0000-0000-0000-000000000000"),
    CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    AccountId = new Guid("00002124-0000-0000-0000-000000000000"),
    CashAmount = "cash_amount0",
    Currency = Currency173.Eur,
    Status = Status72.Settled,
    Orders = new List<AccountLiquidation1>
    {
        new AccountLiquidation1
        {
            Id = new Guid("0000181c-0000-0000-0000-000000000000"),
            Side = "SELL",
            Status = Status73.New,
        },
    },
    FeeCollectionId = new Guid("00001ea2-0000-0000-0000-000000000000"),
    UserId = new Guid("00000780-0000-0000-0000-000000000000"),
    BusinessId = new Guid("0000102e-0000-0000-0000-000000000000"),
};
```

