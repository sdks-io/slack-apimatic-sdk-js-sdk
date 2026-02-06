
# Admin Conversations Set Conversation Prefs Error Schema Error

Schema for error response from admin.conversations.setConversationPrefs

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsSetConversationPrefsErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error10`](../../doc/models/error-10.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "channel_not_found",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

