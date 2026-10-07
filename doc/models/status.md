
# Status

Deprecated: do not build new integrations on this field. Status of the user. To know when the user has met the onboarding requirements for an account group or business, listen for the `ROLE.ACTIVATED` webhook event of the user's role (for example, the `OWNER` role for a `PERSONAL` account group). To track offboarding, listen for the `USER.OFFBOARDING_INITIATED` and `USER.OFFBOARDED` webhook events.

* ACTIVE -
* INACTIVE -
* OFFBOARDING -
* OFFBOARDED -

## Enumeration

`Status`

## Fields

| Name |
|  --- |
| `Active` |
| `Inactive` |
| `Offboarding` |
| `Offboarded` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Status status = Status.Active;
```

