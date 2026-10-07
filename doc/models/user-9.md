
# User 9

The end user that the report is addressed to.

*This model accepts additional fields of type object.*

## Structure

`User9`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FirstName` | `string` | Optional | First name of the user.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `100` |
| `LastName` | `string` | Optional | Last name of the user.<br><br>**Constraints**: *Minimum Length*: `2`, *Maximum Length*: `100` |
| `Salutation` | [`Salutation10?`](../../doc/models/salutation-10.md) | Optional | The salutation used for the end user in reports and statements.<br><br>* SALUTATION_MALE — Herr.<br>* SALUTATION_FEMALE — Frau.<br>* SALUTATION_FEMALE_MARRIED — Frau, married form.<br>* SALUTATION_DIVERSE — Gender-neutral salutation.<br><br>An empty string means no salutation is printed. |
| `Title` | [`Title10?`](../../doc/models/title-10.md) | Optional | The academic title used for the end user in reports and statements.<br><br>* DR — Doctor.<br>* PROF — Professor.<br>* PROF_DR — Professor Doctor.<br>* DIPL_ING — Graduate engineer (Diplom-Ingenieur).<br>* MAGISTER — Magister.<br><br>An empty string means no title is printed. |
| `Address` | [`Address30`](../../doc/models/address-30.md) | Optional | The residential address of the end user, as printed on the report. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

User9 user9 = new User9
{
    FirstName = "first_name8",
    LastName = "last_name6",
    Salutation = Salutation10.SalutationMale,
    Title = Title10.Prof,
    Address = new Address30
    {
        AddressLine1 = "address_line10",
        AddressLine2 = "address_line28",
        Postcode = "postcode0",
        Country = "country0",
        State = "state2",
        ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
    },
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

