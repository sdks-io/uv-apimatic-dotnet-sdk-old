
# Type 12

Relation of the user to the account group.

* `OWNER` — The user owns the account group. A `JOINT` account group has exactly 2 `OWNER` users.
* `CHILD` — The user is the child in a child account group.
* `GUARDIAN` — The user is a guardian of a child account group.

## Enumeration

`Type12`

## Fields

| Name |
|  --- |
| `Owner` |
| `Child` |
| `Guardian` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Type12 type12 = Type12.Guardian;
```

