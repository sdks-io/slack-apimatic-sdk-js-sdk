
# Admin Conversations Search Error Schema Error

Schema for error response from admin.conversations.search

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsSearchErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsSearchErrorEnum`](../../doc/models/admin-conversations-search-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_cursor",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

