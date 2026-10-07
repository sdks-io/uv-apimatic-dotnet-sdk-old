
# Transaction Fee Account Group Configuration Update Request

## Structure

`TransactionFeeAccountGroupConfigurationUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FeeModelId` | `Guid` | Required | Universally Unique Identifier (UUID) of the transaction fee model. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

TransactionFeeAccountGroupConfigurationUpdateRequest transactionFeeAccountGroupConfigurationUpdateRequest = new TransactionFeeAccountGroupConfigurationUpdateRequest
{
    FeeModelId = new Guid("00001806-0000-0000-0000-000000000000"),
};
```

