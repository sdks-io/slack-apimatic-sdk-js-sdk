
# Auth Revoke Schema

Schema for successful response from auth.revoke method

*This model accepts additional fields of type unknown.*

## Structure

`AuthRevokeSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `revoked` | `boolean` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "revoked": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

