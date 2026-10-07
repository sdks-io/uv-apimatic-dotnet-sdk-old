
# Tax Wrappers Create Isa Tax Wrapper Request

Request body for creating an ISA tax wrapper on an account group.

## Structure

`TaxWrappersCreateIsaTaxWrapperRequest`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AccountGroupId` | `Guid` | Required | The ID of the account group to which the tax wrapper belongs. |
| `Type` | `string` | Required, Constant | The kind of ISA that the tax wrapper represents.<br><br>* STOCKS_AND_SHARES_ISA — A Stocks and Shares ISA.<br><br>**Value**: `"STOCKS_AND_SHARES_ISA"` |
| `IsFlexible` | `bool` | Required | True if ISA is flexible. |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

TaxWrappersCreateIsaTaxWrapperRequest taxWrappersCreateIsaTaxWrapperRequest = new TaxWrappersCreateIsaTaxWrapperRequest
{
    AccountGroupId = new Guid("0000167a-0000-0000-0000-000000000000"),
    Type = "STOCKS_AND_SHARES_ISA",
    IsFlexible = false,
};
```

