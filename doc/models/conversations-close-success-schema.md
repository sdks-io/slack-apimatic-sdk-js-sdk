
# Conversations Close Success Schema

Schema for successful response conversations.close method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsCloseSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `alreadyClosed` | `boolean \| undefined` | Optional | - |
| `noOp` | `boolean \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "already_closed": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

