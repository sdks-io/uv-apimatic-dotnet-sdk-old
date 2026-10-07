
# User

*This model accepts additional fields of type object.*

## Structure

`User`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid?` | Optional | Unique identifier of the user, as a UUID. |
| `Type` | [`Type12?`](../../doc/models/type-12.md) | Optional | Relation of the user to the account group.<br><br>* `OWNER` — The user owns the account group. A `JOINT` account group has exactly 2 `OWNER` users.<br>* `CHILD` — The user is the child in a child account group.<br>* `GUARDIAN` — The user is a guardian of a child account group. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

User user = new User
{
    Id = new Guid("0000143c-0000-0000-0000-000000000000"),
    Type = Type12.Guardian,
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

