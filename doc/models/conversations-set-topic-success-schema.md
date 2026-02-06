
# Conversations Set Topic Success Schema

Schema for successful response from conversations.setTopic method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsSetTopicSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `unknown` | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "channel": {
    "key1": "val1",
    "key2": "val2"
  },
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

