
# Tax Exemption German Tax Exemption Details

The German tax exemption details returned for a tax exemption order, including the allowance granted and the amounts used and remaining for the tax year.

## Structure

`TaxExemptionGermanTaxExemptionDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TaxExemptionType` | [`TaxExemptionType`](../../doc/models/tax-exemption-type.md) | Required | Tax exemption type<br><br>* SINGLE - Tax exemption for Individual.<br>* MARRIED - Tax exemption for married couples.<br>* CIVIL_PARTNERSHIP - Tax exemption for registered civil partnerships. |
| `TaxExemptionAmount` | [`TaxExemptionCreateRequestTaxExemptionDetailsAmount`](../../doc/models/tax-exemption-create-request-tax-exemption-details-amount.md) | Required | A monetary amount relating to a tax exemption order, with its [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency. |
| `UtilizedAmount` | [`TaxExemptionCreateRequestTaxExemptionDetailsAmount`](../../doc/models/tax-exemption-create-request-tax-exemption-details-amount.md) | Required | A monetary amount relating to a tax exemption order, with its [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency. |
| `RemainingAmount` | [`TaxExemptionCreateRequestTaxExemptionDetailsAmount`](../../doc/models/tax-exemption-create-request-tax-exemption-details-amount.md) | Required | A monetary amount relating to a tax exemption order, with its [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

TaxExemptionGermanTaxExemptionDetails taxExemptionGermanTaxExemptionDetails = new TaxExemptionGermanTaxExemptionDetails
{
    TaxExemptionType = TaxExemptionType.Single,
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
};
```

