
# Conversations Join Success Schema

Schema for successful response from conversations.join method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsJoinSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `unknown` | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `responseMetadata` | [`ResponseMetadata3 \| undefined`](../../doc/models/response-metadata-3.md) | Optional | - |
| `warning` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "channel": {
    "key1": "val1",
    "key2": "val2"
  },
  "ok": "True",
  "response_metadata": {
    "warnings": [
      "warnings8",
      "warnings9",
      "warnings0"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "warning": "warning4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

