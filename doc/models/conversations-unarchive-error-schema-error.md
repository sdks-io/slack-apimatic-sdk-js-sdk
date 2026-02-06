
# Conversations Unarchive Error Schema Error

Schema for error response from conversations.unarchive method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsUnarchiveErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`Error48`](../../doc/models/error-48.md) | Required | - |
| `needed` | `string \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `provided` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_form_data",
  "ok": "False",
  "callstack": "callstack2",
  "needed": "needed6",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

