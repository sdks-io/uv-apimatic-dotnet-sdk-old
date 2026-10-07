
# Salutation 10

The salutation used for the end user in reports and statements.

* SALUTATION_MALE — Herr.
* SALUTATION_FEMALE — Frau.
* SALUTATION_FEMALE_MARRIED — Frau, married form.
* SALUTATION_DIVERSE — Gender-neutral salutation.

An empty string means no salutation is printed.

## Enumeration

`Salutation10`

## Fields

| Name |
|  --- |
| `SalutationMale` |
| `SalutationFemale` |
| `SalutationFemaleMarried` |
| `SalutationDiverse` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Salutation10 salutation10 = Salutation10.SalutationMale;
```

