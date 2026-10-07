
# Tax Wrappers Isa Allowance

The subscription allowance of an ISA tax wrapper for one tax year, tracking how much of the regulatory limit has been used and how much remains.

## Structure

`TaxWrappersIsaAllowance`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid` | Required | Allowance unique identifier. |
| `CreatedAt` | `DateTime` | Required | The date and time the tax wrapper was created. |
| `UpdatedAt` | `DateTime` | Required | The date and time the tax wrapper was last updated. |
| `TaxWrapperId` | `Guid` | Required | Tax wrapper unique identifier. |
| `TaxYear` | `string` | Optional | The UK tax year the allowance applies to, in `yyyy/yyyy` form. The UK tax year runs from 6 April to 5 April.<br><br>**Constraints**: *Pattern*: `^[0-9]{4}/[0-9]{4}$` |
| `Type` | `string` | Required, Constant | Type of the allowance:<br><br>* ANNUAL - Allowance valid for a tax year.<br><br>**Value**: `"ANNUAL"` |
| `Status` | [`Status57`](../../doc/models/status-57.md) | Required | Status of the allowance:<br><br>* ACTIVE - Current allowance.<br>* EXPIRED - Allowance from previous years. |
| `Currency` | `string` | Required, Constant | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* GBP — Pound Sterling.<br><br>**Value**: `"GBP"` |
| `UsedAmount` | `string` | Required | **Constraints**: *Pattern*: `^-?[0-9]{1,9}(\.[0-9]{2})?$` |
| `RemainingAmount` | `string` | Required | **Constraints**: *Pattern*: `^-?[0-9]{1,9}(\.[0-9]{2})?$` |
| `ValidFrom` | `DateTime` | Required | The date from which the allowance is valid. |
| `ValidTo` | `DateTime?` | Optional | The date and time at which the allowance expires. Expired allowances do not roll over; a new allowance is created for the next tax year. Applies to allowances of type `ANNUAL`. |
| `FirstSubscriptionAt` | `DateTime?` | Optional | The date and time of the first qualifying cash subscription against this allowance. Used for HMRC reporting. |

## Example

```csharp
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;

TaxWrappersIsaAllowance taxWrappersIsaAllowance = new TaxWrappersIsaAllowance
{
    Id = new Guid("00001ff6-0000-0000-0000-000000000000"),
    CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    TaxWrapperId = new Guid("0000094a-0000-0000-0000-000000000000"),
    Type = "ANNUAL",
    Status = Status57.Active,
    Currency = "GBP",
    UsedAmount = "used_amount0",
    RemainingAmount = "remaining_amount2",
    ValidFrom = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    TaxYear = "tax_year4",
    ValidTo = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    FirstSubscriptionAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
};
```

