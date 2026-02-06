
# Admin Conversations Get Teams Schema

Schema for successful response of admin.conversations.getTeams

*This model accepts additional fields of type unknown.*

## Structure

`AdminConversationsGetTeamsSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `responseMetadata` | [`ResponseMetadata \| undefined`](../../doc/models/response-metadata.md) | Optional | - |
| `teamIds` | `string[]` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "team_ids": [
    "team_ids9",
    "team_ids0"
  ],
  "response_metadata": {
    "next_cursor": "next_cursor2",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

