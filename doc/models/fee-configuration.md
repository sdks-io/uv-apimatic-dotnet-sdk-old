
# Fee Configuration

A transaction fee model. Defines how per-order transaction fees are calculated, as a set of tiers with either absolute cash amounts or relative basis-point values. Assign a model to an order via the `fee_configuration` array when placing the order.

## Structure

`FeeConfiguration`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Id` | `Guid` | Required | Universally Unique Identifier (UUID) of the transaction fee model. |
| `CreatedAt` | `DateTime` | Required | Date and time when the resource was created. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `UpdatedAt` | `DateTime` | Required | Date and time when the resource was last updated. [RFC 3339-5](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6), [ISO8601 UTC](https://www.iso.org/iso-8601-date-and-time-format.html) |
| `Label` | `string` | Required | A human-readable label for the transaction fee model. |
| `Currency` | [`Currency`](../../doc/models/currency.md) | Required | Alphabetic three-letter [ISO 4217](https://www.iso.org/iso-4217-currency-codes.html) currency code.<br><br>* EUR — Euro.<br>* GBP — Pound Sterling. |
| `ChargeMethod` | [`FeeChargeMethod1`](../../doc/models/fee-charge-method-1.md) | Required | Indicates how the transaction fee is charged.<br><br>* `CHARGED_BY_CLIENT` — The fee is charged by the client as part of post-trade settlement; the fee movement occurs outside Upvest cash balances.<br>* `COLLECTED_BY_UPVEST` — The fee is charged by the client and collected by Upvest; the fee amount is debited from the user's Upvest cash balance. |
| `ValueType` | [`ValueType`](../../doc/models/value-type.md) | Required | The value type of the transaction fee model.<br><br>* `ABSOLUTE` — Tier fees are fixed cash amounts.<br>* `RELATIVE` — Tier fees are percentages of the order value, expressed in basis points. |
| `ApplicationType` | `string` | Required, Constant | The application type of the transaction fee model.<br><br>* `VOLUME` — The full order value is assessed against the tier thresholds, and the matching tier's fee applies to the total order volume.<br><br>**Value**: `"VOLUME"` |
| `BaseAmountScope` | [`BaseAmountScope`](../../doc/models/base-amount-scope.md) | Required | The scope of the base amount that fee tiers are evaluated against.<br><br>* `GROSS_AMOUNT` — Tiers are evaluated against the gross cash amount of the transaction the fee model is applied to (e.g. the total cash value of an order, a contribution or a transfer).<br>* `ORDER` — Tiers are evaluated against the total cash value of each order. DEPRECATED: Use `GROSS_AMOUNT` instead. Existing fee models using `ORDER` continue to work unchanged. |
| `Tiers` | [`List<FeeConfigurationTiers>`](../../doc/models/containers/fee-configuration-tiers.md) | Required | This is List of a container for one-of cases. |

## Example

```csharp
using System.Collections.Generic;
using System.Globalization;
using UpvestInvestmentApi.Standard.Models;
using UpvestInvestmentApi.Standard.Models.Containers;
using UpvestInvestmentApi.Standard.Utilities;

FeeConfiguration feeConfiguration = new FeeConfiguration
{
    Id = new Guid("00001bf8-0000-0000-0000-000000000000"),
    CreatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    UpdatedAt = DateTime.ParseExact("2016-03-13T12:52:32.123Z", "yyyy'-'MM'-'dd'T'HH':'mm':'ss.FFFFFFFK",
        provider: CultureInfo.InvariantCulture,
        DateTimeStyles.RoundtripKind),
    Label = "label0",
    Currency = Currency.Eur,
    ChargeMethod = FeeChargeMethod1.ChargedByClient,
    ValueType = ValueType.Absolute,
    ApplicationType = "VOLUME",
    BaseAmountScope = BaseAmountScope.GrossAmount,
    Tiers = new List<FeeConfigurationTiers>
    {
        FeeConfigurationTiers.FromAbsoluteTransactionFeeTier(
            new AbsoluteTransactionFeeTier
            {
                TierId = "tier_id8",
                BaseAmountFrom = "base_amount_from0",
                FeeAmount = "fee_amount8",
                ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
            }
        ),
        FeeConfigurationTiers.FromAbsoluteTransactionFeeTier(
            new AbsoluteTransactionFeeTier
            {
                TierId = "tier_id8",
                BaseAmountFrom = "base_amount_from0",
                FeeAmount = "fee_amount8",
                ["exampleAdditionalProperty"] = ApiHelper.JsonDeserialize<object>("{\"key1\":\"val1\",\"key2\":\"val2\"}"),
            }
        ),
    },
};
```

