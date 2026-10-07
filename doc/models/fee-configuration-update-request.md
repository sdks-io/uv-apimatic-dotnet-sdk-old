
# Fee Configuration Update Request

Request body for changing the fee model assigned to an account.

## Structure

`FeeConfigurationUpdateRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `FeeModelId` | `Guid` | Required | The unique identifier of the fee model, as a UUID. Upvest provides this value when a fee model is set up. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

FeeConfigurationUpdateRequest feeConfigurationUpdateRequest = new FeeConfigurationUpdateRequest
{
    FeeModelId = new Guid("00001d6a-0000-0000-0000-000000000000"),
};
```

