
# Conversations Open Success Schema

Schema for successful response from conversations.open method when opening channels, ims, mpims

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsOpenSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `alreadyOpen` | `boolean \| undefined` | Optional | - |
| `channel` | `unknown` | Required | - |
| `noOp` | `boolean \| undefined` | Optional | - |
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
  "already_open": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

