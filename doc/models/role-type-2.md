
# Role Type 2

Role type to assign.

* `GUARDIAN` — The user is a legal custodian of the child account group.
* `OWNER` — The second owner of a `JOINT` account group; the first owner is the user the account group was created with. `custody_type` does not apply.

## Enumeration

`RoleType2`

## Fields

| Name |
|  --- |
| `Guardian` |
| `Owner` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

RoleType2 roleType2 = RoleType2.Guardian;
```

