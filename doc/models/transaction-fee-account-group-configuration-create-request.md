
# Transaction Fee Account Group Configuration Create Request

## Structure

`TransactionFeeAccountGroupConfigurationCreateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FeeModelId` | `Guid` | Required | Universally Unique Identifier (UUID) of the transaction fee model. |
| `AccountGroupId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account group. |
| `TransactionCategory` | [`TransactionCategory`](../../doc/models/transaction-category.md) | Required | The operation type a transaction fee model is assigned to.<br><br>* PENSION_DE_CONTRIBUTION -<br>* PENSION_DE_CONTRIBUTION_GOVERNMENT_BONUS -<br>* PENSION_DE_INCOMING_TRANSFER -<br>* PENSION_DE_OUTGOING_TRANSFER - |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

TransactionFeeAccountGroupConfigurationCreateRequest transactionFeeAccountGroupConfigurationCreateRequest = new TransactionFeeAccountGroupConfigurationCreateRequest
{
    FeeModelId = new Guid("0000081c-0000-0000-0000-000000000000"),
    AccountGroupId = new Guid("0000236a-0000-0000-0000-000000000000"),
    TransactionCategory = TransactionCategory.PensionDeIncomingTransfer,
};
```

