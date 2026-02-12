
# Admin Conversations Unarchive Error Schema Error

Schema for error response from admin.conversations.getConversationPrefs

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsUnarchiveErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsGetConversationPrefsErrorEnum`](../../doc/models/admin-conversations-get-conversation-prefs-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "missing_scope",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

