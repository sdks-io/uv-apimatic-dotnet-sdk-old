
# Document Type 5

The type of document used in the Guardian check. A check carries one document, so a guardian with sole custody submits the birth certificate and the proof of custody as two checks of this type.

* BIRTH_CERTIFICATE - Birth certificate proving guardian relationship
* SOLE_CUSTODY_PROOF - Document proving the guardian holds sole custody of the child. Accepted only when the role identified by role_id has a custody_type of SOLE_CUSTODY.

## Enumeration

`DocumentType5`

## Fields

| Name |
|  --- |
| `BirthCertificate` |
| `SoleCustodyProof` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

DocumentType5 documentType5 = DocumentType5.BirthCertificate;
```

