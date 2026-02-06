
# Dnd Info Schema

Schema for successful response from dnd.info method

*This model accepts additional fields of type unknown.*

## Structure

`DndInfoSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `dndEnabled` | `boolean` | Required | - |
| `nextDndEndTs` | `number` | Required | - |
| `nextDndStartTs` | `number` | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `snoozeEnabled` | `boolean \| undefined` | Optional | - |
| `snoozeEndtime` | `number \| undefined` | Optional | - |
| `snoozeRemaining` | `number \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "dnd_enabled": false,
  "next_dnd_end_ts": 138,
  "next_dnd_start_ts": 198,
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 96,
  "snooze_remaining": 96,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

