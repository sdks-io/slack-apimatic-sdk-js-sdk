
# Admin Conversations Get Conversation Prefs Schema

Schema for successful response of admin.conversations.getConversationPrefs

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsGetConversationPrefsSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `prefs` | [`Prefs1 \| undefined`](../../doc/models/prefs-1.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "prefs": {
    "can_thread": {
      "type": [
        "type1",
        "type0"
      ],
      "user": [
        "user6",
        "user7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "who_can_post": {
      "type": [
        "type5",
        "type4"
      ],
      "user": [
        "user0",
        "user1"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

