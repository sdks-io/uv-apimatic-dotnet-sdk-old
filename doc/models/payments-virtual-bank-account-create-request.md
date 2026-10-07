
# Payments Virtual Bank Account Create Request

Request body for creating a virtual bank account for an account group.

## Structure

`PaymentsVirtualBankAccountCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AccountGroupId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account group. |
| `Name` | `string` | Required | Name of the virtual bank account |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

PaymentsVirtualBankAccountCreateRequest paymentsVirtualBankAccountCreateRequest = new PaymentsVirtualBankAccountCreateRequest
{
    AccountGroupId = new Guid("00001f6a-0000-0000-0000-000000000000"),
    Name = "name2",
};
```

