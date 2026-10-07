
# Type 13

Account group type.

* PERSONAL - Account group of a person holding assets on their own behalf.
* LEGAL_ENTITY - Account group of a legal entity holding assets on behalf of their users.
* FRENCH_PEA - Account group of a french resident holding assets in Plan d'Epargne en Actions.
* ISA - Account group of a UK resident holding assets in an individual savings account.
* CHILD - Account group of a child user holding assets in a child account.
* JOINT - Account group legally and beneficially owned by exactly 2 users. The user the account group is created with becomes the first owner and receives an OWNER role. The second owner is added by creating an OWNER role for them (POST /roles); no further owners can be added. The account group activates only once both OWNER roles are active.

## Enumeration

`Type13`

## Fields

| Name |
|  --- |
| `Personal` |
| `LegalEntity` |
| `FrenchPea` |
| `Isa` |
| `Child` |
| `Joint` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Type13 type13 = Type13.Personal;
```

