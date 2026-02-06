
# Users Info Success Schema

Schema for successful response from users.info method

*This model accepts additional fields of type unknown.*

## Structure

`UsersInfoSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `user` | `unknown` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "user": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

