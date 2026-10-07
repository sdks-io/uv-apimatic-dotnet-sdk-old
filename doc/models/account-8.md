
# Account 8

The account that the planned order would be placed for.

*This model accepts additional fields of type object.*

## Structure

`Account8`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid?` | Optional | Universally Unique Identifier (UUID) of the account. |
| `AccountNumber` | `int?` | Optional | The serial account number of the account in the account group.<br><br>**Constraints**: `>= 1` |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

Account8 account8 = new Account8
{
    Id = new Guid("00001b6e-0000-0000-0000-000000000000"),
    AccountNumber = 10,
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

