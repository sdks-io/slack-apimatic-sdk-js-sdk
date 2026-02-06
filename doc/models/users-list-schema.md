
# Users List Schema

Schema for successful response from users.list method

*This model accepts additional fields of type unknown.*

## Structure

`UsersListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cacheTs` | `number` | Required | - |
| `members` | `unknown[]` | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `responseMetadata` | `unknown \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "cache_ts": 154,
  "members": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
  "response_metadata": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

