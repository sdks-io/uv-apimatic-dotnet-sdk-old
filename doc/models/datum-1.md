
# Datum 1

The account's holding of a specific instrument, including the total quantity and how much of it is locked for trading, pending settlement, available for trading, available for instruction, or settled.

## Structure

`Datum1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `AccountId` | `Guid` | Required | Universally Unique Identifier (UUID) of the account. |
| `Instrument` | [`Instrument`](../../doc/models/instrument.md) | Required | The instrument this position is held in, identified by its `uuid` and, if assigned, its `isin`. |
| `Quantity` | `string` | Required | **Constraints**: *Pattern*: `^-?[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `LockedForTrading` | `string` | Required | A positive decimal amount, as a string.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `PendingSettlement` | `string` | Required | A positive decimal amount, as a string.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `AvailableForTrading` | `string` | Required | **Constraints**: *Pattern*: `^-?[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `AvailableForInstruction` | `string` | Required | **Constraints**: *Pattern*: `^-?[0-9]{0,63}(\.[0-9]{1,27})?$` |
| `SettledQuantity` | `string` | Required | A positive decimal amount, as a string.<br><br>**Constraints**: *Pattern*: `^[0-9]{0,63}(\.[0-9]{1,27})?$` |

## Example

```csharp
using UpvestInvestmentApi.Standard.Models;

Datum1 datum1 = new Datum1
{
    AccountId = new Guid("000005be-0000-0000-0000-000000000000"),
    Instrument = new Instrument
    {
        Uuid = new Guid("00001fd8-0000-0000-0000-000000000000"),
        Isin = "isin4",
    },
    Quantity = "quantity4",
    LockedForTrading = "locked_for_trading2",
    PendingSettlement = "pending_settlement2",
    AvailableForTrading = "available_for_trading6",
    AvailableForInstruction = "available_for_instruction0",
    SettledQuantity = "settled_quantity0",
};
```

