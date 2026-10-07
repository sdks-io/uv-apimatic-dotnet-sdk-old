
# Fee Configuration Create Request 1

Request body for assigning a fee model to an account.

## Structure

`FeeConfigurationCreateRequest1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AccountId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account. |
| `FeeModelId` | `Guid` | Required | The unique identifier of the fee model, as a UUID. Upvest provides this value when a fee model is set up. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

FeeConfigurationCreateRequest1 feeConfigurationCreateRequest1 = new FeeConfigurationCreateRequest1
{
    AccountId = new Guid("00001d34-0000-0000-0000-000000000000"),
    FeeModelId = new Guid("00001abc-0000-0000-0000-000000000000"),
};
```

