
# Conversations Close Error Schema Error

Schema for error response from conversations.close method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsCloseErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`Error31`](../../doc/models/error-31.md) | Required | - |
| `needed` | `string \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `provided` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_json",
  "ok": "False",
  "callstack": "callstack4",
  "needed": "needed2",
  "provided": "provided4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

