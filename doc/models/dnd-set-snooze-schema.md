
# Dnd Set Snooze Schema

Schema for successful response from dnd.setSnooze method

*This model accepts additional fields of type unknown.*

## Structure

`DndSetSnoozeSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `snoozeEnabled` | `boolean` | Required | - |
| `snoozeEndtime` | `number` | Required | - |
| `snoozeRemaining` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 8,
  "snooze_remaining": 8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

