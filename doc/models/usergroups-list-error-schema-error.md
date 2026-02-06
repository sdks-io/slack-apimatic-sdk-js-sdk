
# Usergroups List Error Schema Error

Schema for error response from usergroups.list method

*This model accepts additional fields of type unknown.*

## Structure

`UsergroupsListErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`Error84`](../../doc/models/error-84.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "not_authed",
  "ok": "False",
  "callstack": "callstack0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

