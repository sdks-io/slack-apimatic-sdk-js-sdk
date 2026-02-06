
# Objs Reminder

*This model accepts additional fields of type unknown.*

## Structure

`ObjsReminder`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `completeTs` | `number \| undefined` | Optional | - |
| `creator` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^Rm[A-Z0-9]{8,}$` |
| `recurring` | `boolean` | Required | - |
| `text` | `string` | Required | - |
| `time` | `number \| undefined` | Optional | - |
| `user` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "complete_ts": 102,
  "creator": "creator4",
  "id": "id6",
  "recurring": false,
  "text": "text4",
  "time": 252,
  "user": "user6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

