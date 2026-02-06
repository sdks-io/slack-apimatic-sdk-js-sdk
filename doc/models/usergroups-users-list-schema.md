
# Usergroups Users List Schema

Schema for successful response from usergroups.users.list method

*This model accepts additional fields of type unknown.*

## Structure

`UsergroupsUsersListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `users` | `string[]` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "users": [
    "users3"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

