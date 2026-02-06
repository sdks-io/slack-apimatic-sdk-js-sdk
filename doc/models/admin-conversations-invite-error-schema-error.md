
# Admin Conversations Invite Error Schema Error

Schema for error response from admin.conversations.invite

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsInviteErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error7`](../../doc/models/error-7.md) | Required | - |
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

