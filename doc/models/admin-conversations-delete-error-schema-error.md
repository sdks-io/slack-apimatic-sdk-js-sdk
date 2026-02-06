
# Admin Conversations Delete Error Schema Error

Schema for error response from admin.conversations.delete

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsDeleteErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error3`](../../doc/models/error-3.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "could_not_delete_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

