
# Subteam Usergroup Object

*This model accepts additional fields of type unknown.*

## Structure

`SubteamUsergroupObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `autoProvision` | `boolean` | Required | - |
| `autoType` | `unknown` | Required | - |
| `channelCount` | `number \| undefined` | Optional | - |
| `createdBy` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `dateCreate` | `number` | Required | - |
| `dateDelete` | `number` | Required | - |
| `dateUpdate` | `number` | Required | - |
| `deletedBy` | `unknown` | Required | - |
| `description` | `string` | Required | - |
| `enterpriseSubteamId` | `string` | Required | - |
| `handle` | `string` | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^S[A-Z0-9]{2,}$` |
| `isExternal` | `boolean` | Required | - |
| `isSubteam` | `boolean` | Required | - |
| `isUsergroup` | `boolean` | Required | - |
| `name` | `string` | Required | - |
| `prefs` | [`Prefs`](../../doc/models/prefs.md) | Required | - |
| `teamId` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `updatedBy` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `userCount` | `number \| undefined` | Optional | - |
| `users` | `string[] \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "auto_provision": false,
  "auto_type": {
    "key1": "val1",
    "key2": "val2"
  },
  "channel_count": 140,
  "created_by": "created_by4",
  "date_create": 240,
  "date_delete": 32,
  "date_update": 18,
  "deleted_by": {
    "key1": "val1",
    "key2": "val2"
  },
  "description": "description2",
  "enterprise_subteam_id": "enterprise_subteam_id6",
  "handle": "handle4",
  "id": "id8",
  "is_external": false,
  "is_subteam": false,
  "is_usergroup": false,
  "name": "name8",
  "prefs": {
    "channels": [
      "channels5",
      "channels4"
    ],
    "groups": [
      "groups4",
      "groups5",
      "groups6"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "team_id": "team_id8",
  "updated_by": "updated_by2",
  "user_count": 110,
  "users": [
    "users5",
    "users4"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

