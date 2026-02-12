
# Admin Conversations Convert to Private Error Schema Error

Schema for error response from admin.conversations.convertToPrivate

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsConvertToPrivateErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsConvertToPrivateErrorEnum`](../../doc/models/admin-conversations-convert-to-private-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "default_org_wide_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

