
# Users Info Error Schema Error

Schema for error response from users.info method

*This model accepts additional fields of type unknown.*

## Structure

`UsersInfoErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | - |
| `error` | [`Error92`](../../doc/models/error-92.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "not_authed",
  "ok": "False",
  "callstack": "callstack4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

