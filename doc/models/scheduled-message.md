
# Scheduled Message

*This model accepts additional fields of type unknown.*

## Structure

`ScheduledMessage`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channelId` | `string` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `dateCreated` | `number` | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^[Q][A-Z0-9]{8,}$` |
| `postAt` | `number` | Required | - |
| `text` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "channel_id": "channel_id4",
  "date_created": 228,
  "id": "id8",
  "post_at": 128,
  "text": "text8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

