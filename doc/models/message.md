
# Message

*This model accepts additional fields of type unknown.*

## Structure

`Message`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `botId` | `string` | Required | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `botProfile` | [`BotProfileObject \| undefined`](../../doc/models/bot-profile-object.md) | Optional | - |
| `team` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `text` | `string` | Required | - |
| `type` | `string` | Required | - |
| `user` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `username` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "bot_id": "bot_id0",
  "bot_profile": {
    "app_id": "app_id8",
    "deleted": false,
    "icons": {
      "image_36": "image_362",
      "image_48": "image_488",
      "image_72": "image_722",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "id": "id8",
    "name": "name8",
    "team_id": "team_id8",
    "updated": 44,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "team": "team4",
  "text": "text4",
  "type": "type4",
  "user": "user6",
  "username": "username4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

