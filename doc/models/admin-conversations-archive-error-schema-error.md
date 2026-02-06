
# Admin Conversations Archive Error Schema Error

Schema for error response from admin.conversations.archive

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsArchiveErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error`](../../doc/models/error.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "already_archived",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

