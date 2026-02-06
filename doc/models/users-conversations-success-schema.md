
# Users Conversations Success Schema

Schema for successful response from users.conversations method. Returned conversation objects do not include `num_members` or `is_member`

*This model accepts additional fields of type unknown.*

## Structure

`UsersConversationsSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channels` | `unknown[]` | Required | **Constraints**: *Unique Items Required* |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `responseMetadata` | [`ResponseMetadata \| undefined`](../../doc/models/response-metadata.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
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

