
# Tax Exemption Create Request Tax Exemption Details Amount

A monetary amount relating to a tax exemption order, with its [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency.

## Structure

`TaxExemptionCreateRequestTaxExemptionDetailsAmount`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Amount` | `string` | Required | A positive cash amount, as a decimal string with up to two decimal places.<br><br>**Constraints**: *Pattern*: `^[0-9]{1,9}(\.[0-9]{2})?$` |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Required | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* EUR — Euro.<br>* GBP — Pound Sterling. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

TaxExemptionCreateRequestTaxExemptionDetailsAmount taxExemptionCreateRequestTaxExemptionDetailsAmount = new TaxExemptionCreateRequestTaxExemptionDetailsAmount
{
    Amount = "amount6",
    Currency = Currency.Eur,
};
```

