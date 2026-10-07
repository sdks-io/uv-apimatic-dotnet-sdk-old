
# Transaction Fee Account Group Configuration

## Structure

`TransactionFeeAccountGroupConfiguration`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid` | Required | Transaction fee account group configuration unique identifier. |
| `CreatedAt` | `DateTime` | Required | Date and time when the resource was created. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `UpdatedAt` | `DateTime` | Required | Date and time when the resource was last updated. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `FeeModelId` | `Guid` | Required | Universally Unique Identifier (UUID) of the transaction fee model. |
| `AccountGroupId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account group. |
| `TransactionCategory` | [`TransactionCategory`](../../doc/models/transaction-category.md) | Required | The operation type a transaction fee model is assigned to.<br><br>* PENSION_DE_CONTRIBUTION -<br>* PENSION_DE_CONTRIBUTION_GOVERNMENT_BONUS -<br>* PENSION_DE_INCOMING_TRANSFER -<br>* PENSION_DE_OUTGOING_TRANSFER - |

## Example

```csharp
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;

TransactionFeeAccountGroupConfiguration transactionFeeAccountGroupConfiguration = new TransactionFeeAccountGroupConfiguration
{
    Id = new Guid("0000241c-0000-0000-0000-000000000000"),
    CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    FeeModelId = new Guid("00001b48-0000-0000-0000-000000000000"),
    AccountGroupId = new Guid("00000f86-0000-0000-0000-000000000000"),
    TransactionCategory = TransactionCategory.PensionDeIncomingTransfer,
};
```

