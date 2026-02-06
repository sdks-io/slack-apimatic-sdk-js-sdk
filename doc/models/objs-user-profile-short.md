
# Objs User Profile Short

*This model accepts additional fields of type unknown.*

## Structure

`ObjsUserProfileShort`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `avatarHash` | `string` | Required | - |
| `displayName` | `string` | Required | - |
| `displayNameNormalized` | `string \| undefined` | Optional | - |
| `firstName` | `string \| null` | Required | - |
| `image72` | `string` | Required | - |
| `isRestricted` | `boolean` | Required | - |
| `isUltraRestricted` | `boolean` | Required | - |
| `name` | `string` | Required | - |
| `realName` | `string` | Required | - |
| `realNameNormalized` | `string \| undefined` | Optional | - |
| `team` | `string` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash2",
  "display_name": "display_name2",
  "display_name_normalized": "display_name_normalized2",
  "first_name": "first_name2",
  "image_72": "image_726",
  "is_restricted": false,
  "is_ultra_restricted": false,
  "name": "name2",
  "real_name": "real_name8",
  "real_name_normalized": "real_name_normalized4",
  "team": "team8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

