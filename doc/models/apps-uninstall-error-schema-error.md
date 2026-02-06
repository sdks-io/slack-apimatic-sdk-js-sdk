
# Apps Uninstall Error Schema Error

Schema for error response from apps.uninstall method

*This model accepts additional fields of type unknown.*

## Structure

`AppsUninstallErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`Error16`](../../doc/models/error-16.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "client_id_token_mismatch",
  "ok": "False",
  "callstack": "callstack4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

