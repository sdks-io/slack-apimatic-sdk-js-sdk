
# Admin Conversations Disconnect Shared Error Schema Error

Schema for error response from admin.conversations.disconnectShared

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsDisconnectSharedErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`AdminConversationsDisconnectSharedErrorEnum`](../../doc/models/admin-conversations-disconnect-shared-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "leaving_team_not_in_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

