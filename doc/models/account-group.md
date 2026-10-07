
# Account Group

An account group owned by a user. Aggregates its accounts for tax calculation and regulatory reporting, holds positions in the form of cash, and carries the official securities account number.

## Structure

`AccountGroup`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid` | Required | Universally Unique Identifier (UUID) of the account group. |
| `CreatedAt` | `DateTime` | Required | Date and time when the resource was created. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `UpdatedAt` | `DateTime` | Required | Date and time when the resource was last updated. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `Users` | [`List<User>`](../../doc/models/user.md) | Required | The users associated with the account group, each with their relation type. |
| `Status` | [`Status18`](../../doc/models/status-18.md) | Required | Status of the account group.<br><br>* `PENDING_APPROVAL` — Account group approval is pending — the account group is visible through our API but cannot be acted on.<br>* `ACTIVE` — Account group is active — full functionality of the Investment API is accessible.<br>* `CLOSING` — Account group is closing.<br>* `CLOSED` — Account group is closed.<br>* `LOCKED` — Account group is locked for all actions. |
| `Type` | [`Type13`](../../doc/models/type-13.md) | Required | Account group type.<br><br>* PERSONAL - Account group of a person holding assets on their own behalf.<br>* LEGAL_ENTITY - Account group of a legal entity holding assets on behalf of their users.<br>* FRENCH_PEA - Account group of a french resident holding assets in Plan d'Epargne en Actions.<br>* ISA - Account group of a UK resident holding assets in an individual savings account.<br>* CHILD - Account group of a child user holding assets in a child account.<br>* JOINT - Account group legally and beneficially owned by exactly 2 users. The user the account group is created with becomes the first owner and receives an OWNER role. The second owner is added by creating an OWNER role for them (POST /roles); no further owners can be added. The account group activates only once both OWNER roles are active. |
| `SecuritiesAccountNumber` | `string` | Required | Official securities account number, assigned at account group level. A string of 7 to 12 digits. |

## Example

```csharp
using System.Collections.Generic;
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

AccountGroup accountGroup = new AccountGroup
{
    Id = new Guid("00001a36-0000-0000-0000-000000000000"),
    CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    Users = new List<User>
    {
        new User
        {
            Id = new Guid("0000150a-0000-0000-0000-000000000000"),
            Type = Type12.Child,
            ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
        },
    },
    Status = Status18.Closed,
    Type = Type13.FrenchPea,
    SecuritiesAccountNumber = "securities_account_number0",
};
```

