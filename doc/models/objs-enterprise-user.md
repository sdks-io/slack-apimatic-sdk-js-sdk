
# Objs Enterprise User

*This model accepts additional fields of type unknown.*

## Structure

`ObjsEnterpriseUser`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `enterpriseId` | `string` | Required | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` |
| `enterpriseName` | `string` | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^[WU][A-Z0-9]{8,}$` |
| `isAdmin` | `boolean` | Required | - |
| `isOwner` | `boolean` | Required | - |
| `teams` | `string[]` | Required | **Constraints**: *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "enterprise_id": "enterprise_id0",
  "enterprise_name": "enterprise_name0",
  "id": "id0",
  "is_admin": false,
  "is_owner": false,
  "teams": [
    "teams3",
    "teams4",
    "teams5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

