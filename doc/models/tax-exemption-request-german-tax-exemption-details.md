
# Tax Exemption Request German Tax Exemption Details

The German tax exemption details supplied when creating or updating a tax exemption order.

## Structure

`TaxExemptionRequestGermanTaxExemptionDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `TaxExemptionType` | [`TaxExemptionType?`](../../doc/models/tax-exemption-type.md) | Optional | Tax exemption type<br><br>* SINGLE - Tax exemption for Individual.<br>* MARRIED - Tax exemption for married couples.<br>* CIVIL_PARTNERSHIP - Tax exemption for registered civil partnerships. |
| `TaxExemptionAmount` | [`TaxExemptionCreateRequestTaxExemptionDetailsAmount`](../../doc/models/tax-exemption-create-request-tax-exemption-details-amount.md) | Required | A monetary amount relating to a tax exemption order, with its [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

TaxExemptionRequestGermanTaxExemptionDetails taxExemptionRequestGermanTaxExemptionDetails = new TaxExemptionRequestGermanTaxExemptionDetails
{
    TaxExemptionAmount = new TaxExemptionCreateRequestTaxExemptionDetailsAmount
    {
        Amount = "amount4",
        Currency = Currency.Eur,
    },
    TaxExemptionType = TaxExemptionType.CivilPartnership,
};
```

