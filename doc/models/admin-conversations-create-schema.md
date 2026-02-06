
# Admin Conversations Create Schema

Schema for successful response of admin.conversations.create

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsCreateSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channelId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "channel_id": "channel_id6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

