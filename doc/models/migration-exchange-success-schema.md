
# Migration Exchange Success Schema

Schema for successful response from migration.exchange method

*This model accepts additional fields of type unknown.*

## Structure

`MigrationExchangeSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `enterpriseId` | `string` | Required | - |
| `invalidUserIds` | `string[] \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `teamId` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `userIdMap` | `unknown \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "enterprise_id": "enterprise_id8",
  "ok": "True",
  "team_id": "team_id8",
  "invalid_user_ids": [
    "invalid_user_ids6"
  ],
  "user_id_map": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

