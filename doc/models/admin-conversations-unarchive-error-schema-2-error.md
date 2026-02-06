
# Admin Conversations Unarchive Error Schema 2 Error

Schema for error response from admin.conversations.rename

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsUnarchiveErrorSchema2Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error8`](../../doc/models/error-8.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "name_taken",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

