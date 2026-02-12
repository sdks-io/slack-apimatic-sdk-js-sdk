
# Conversations Set Purpose Error Schema Error

Schema for error response from conversations.setPurpose method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsSetPurposeErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`ConversationsSetPurposeErrorEnum`](../../doc/models/conversations-set-purpose-error-enum.md) | Required | - |
| `needed` | `string \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `provided` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "request_timeout",
  "ok": "False",
  "callstack": "callstack0",
  "needed": "needed4",
  "provided": "provided0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

