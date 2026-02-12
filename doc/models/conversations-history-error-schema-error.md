
# Conversations History Error Schema Error

Schema for error response from conversations.history method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsHistoryErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`ConversationsHistoryErrorEnum`](../../doc/models/conversations-history-error-enum.md) | Required | - |
| `needed` | `string \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `provided` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "missing_scope",
  "ok": "False",
  "callstack": "callstack6",
  "needed": "needed0",
  "provided": "provided6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

