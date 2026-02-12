
# Conversations Kick Error Schema Error

Schema for error response conversations.kick method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsKickErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`ConversationsKickErrorEnum`](../../doc/models/conversations-kick-error-enum.md) | Required | - |
| `needed` | `string \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `provided` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "not_in_channel",
  "ok": "False",
  "callstack": "callstack2",
  "needed": "needed4",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

