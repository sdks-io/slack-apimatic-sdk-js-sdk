
# Dnd End Snooze Schema

Schema for successful response from dnd.endSnooze method

*This model accepts additional fields of type unknown.*

## Structure

`DndEndSnoozeSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `dndEnabled` | `boolean` | Required | - |
| `nextDndEndTs` | `number` | Required | - |
| `nextDndStartTs` | `number` | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `snoozeEnabled` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "dnd_enabled": false,
  "next_dnd_end_ts": 248,
  "next_dnd_start_ts": 88,
  "ok": "True",
  "snooze_enabled": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

