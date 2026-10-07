
# Key

*This model accepts additional fields of type object.*

## Structure

`Key`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Kid` | `Guid?` | Optional | The identifier of the key, matching the `kid` in the signature header of a webhook payload. |
| `Kty` | [`Kty?`](../../doc/models/kty.md) | Optional | The cryptographic algorithm family of the key.<br><br>* EC — Elliptic curve.<br><br>**Default**: `Kty.EC` |
| `Crv` | [`Crv?`](../../doc/models/crv.md) | Optional | The elliptic curve the key uses.<br><br>* P-521 — NIST P-521.<br><br>**Default**: `Crv.P521` |
| `X` | `string` | Optional | The x coordinate of the elliptic curve point, base64url encoded. |
| `Y` | `string` | Optional | The y coordinate of the elliptic curve point, base64url encoded. |
| `AdditionalProperties` | `object this[string key]` | Optional | - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Utilities;

Key key = new Key
{
    Kid = new Guid("00000132-0000-0000-0000-000000000000"),
    Kty = Kty.Ec,
    Crv = Crv.P521,
    X = "x6",
    Y = "y4",
    ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
};
```

