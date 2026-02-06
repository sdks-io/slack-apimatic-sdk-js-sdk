
# Apps Permissions Info Error Schema Error

Schema for error response from apps.permissions.info method

*This model accepts additional fields of type unknown.*

## Structure

`AppsPermissionsInfoErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`Error12`](../../doc/models/error-12.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "token_revoked",
  "ok": "False",
  "callstack": "callstack4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

