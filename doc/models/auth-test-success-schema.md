
# Auth Test Success Schema

Schema for successful response auth.test method

*This model accepts additional fields of type unknown.*

## Structure

`AuthTestSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `botId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `isEnterpriseInstall` | `boolean \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `team` | `string` | Required | - |
| `teamId` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `url` | `string` | Required | - |
| `user` | `string` | Required | - |
| `userId` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "team": "team0",
  "team_id": "team_id4",
  "url": "url4",
  "user": "user0",
  "user_id": "user_id8",
  "bot_id": "bot_id6",
  "is_enterprise_install": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

