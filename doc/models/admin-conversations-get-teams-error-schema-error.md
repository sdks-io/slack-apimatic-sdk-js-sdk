
# Admin Conversations Get Teams Error Schema Error

Schema for error response from admin.conversations.getTeams

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsGetTeamsErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsGetTeamsErrorEnum`](../../doc/models/admin-conversations-get-teams-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "channel_type_not_supported",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

