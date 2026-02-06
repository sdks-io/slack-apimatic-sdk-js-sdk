
# Conversations Leave Success Schema

Schema for successful response from conversations.leave method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsLeaveSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `notInChannel` | `boolean \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "not_in_channel": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

