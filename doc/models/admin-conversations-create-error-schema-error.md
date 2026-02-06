
# Admin Conversations Create Error Schema Error

Schema for error response from admin.conversations.create

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsCreateErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error2`](../../doc/models/error-2.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "could_not_create_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

