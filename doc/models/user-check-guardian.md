
# User Check Guardian

The Guardian check is completed by the client providing documentation proving the guardian relationship with the child user.

*This model accepts additional fields of type object.*

## Structure

`UserCheckGuardian`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid` | Required | User Check unique identifier. |
| `UserId` | `Guid` | Required | Unique identifier of the user, as a UUID. |
| `Type` | `string` | Required | The type of check must be “GUARDIAN“.<br><br>**Default**: `"GUARDIAN"` |
| `CheckConfirmedAt` | `DateTime?` | Optional | Completion date and time of the PoR check. |
| `RoleId` | `Guid` | Required | Unique identifier for the role that this guardian check is associated with. |
| `DocumentType` | [`DocumentType5`](../../doc/models/document-type-5.md) | Required | The type of document used in the Guardian check. A check carries one document, so a guardian with sole custody submits the birth certificate and the proof of custody as two checks of this type.<br><br>* BIRTH_CERTIFICATE - Birth certificate proving guardian relationship<br>* SOLE_CUSTODY_PROOF - Document proving the guardian holds sole custody of the child. Accepted only when the role identified by role_id has a custody_type of SOLE_CUSTODY. |
| `DataDownloadLink` | `string` | Required | Download URL for the guardian evidence file. The file size must not exceed 250 MB.<br><br>**Constraints**: *Maximum Length*: `1000` |
| `Status` | [`Status10`](../../doc/models/status-10.md) | Required | Final status of the Guardian check.<br><br>* IN_PROGRESS - Guardian check is in progress<br>* PASSED - Guardian check passed<br>* FAILED - Guardian check failed |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

UserCheckGuardian userCheckGuardian = new UserCheckGuardian
{
    Id = new Guid("000025b4-0000-0000-0000-000000000000"),
    UserId = new Guid("000005b4-0000-0000-0000-000000000000"),
    Type = "GUARDIAN",
    RoleId = new Guid("00001f0c-0000-0000-0000-000000000000"),
    DocumentType = DocumentType5.BirthCertificate,
    DataDownloadLink = "data_download_link4",
    Status = Status10.Failed,
    CheckConfirmedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

