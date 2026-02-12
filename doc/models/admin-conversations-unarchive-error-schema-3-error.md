
# Admin Conversations Unarchive Error Schema 3 Error

Schema for error response from admin.conversations.unarchive

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsUnarchiveErrorSchema3Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsUnarchiveErrorEnum`](../../doc/models/admin-conversations-unarchive-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "restricted_action",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

