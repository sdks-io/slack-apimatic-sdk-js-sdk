
# User Profile Object

*This model accepts additional fields of type unknown.*

## Structure

`UserProfileObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `alwaysActive` | `boolean \| undefined` | Optional | - |
| `apiAppId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^(A[A-Z0-9]{1,})?$` |
| `avatarHash` | `string` | Required | - |
| `botId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `displayName` | `string` | Required | - |
| `displayNameNormalized` | `string` | Required | - |
| `email` | `string \| null \| undefined` | Optional | - |
| `fields` | `unknown[] \| null` | Required | - |
| `firstName` | `string \| null \| undefined` | Optional | - |
| `guestExpirationTs` | `number \| null \| undefined` | Optional | - |
| `guestInvitedBy` | `string \| null \| undefined` | Optional | - |
| `image1024` | `string \| null \| undefined` | Optional | - |
| `image192` | `string \| null \| undefined` | Optional | - |
| `image24` | `string \| null \| undefined` | Optional | - |
| `image32` | `string \| null \| undefined` | Optional | - |
| `image48` | `string \| null \| undefined` | Optional | - |
| `image512` | `string \| null \| undefined` | Optional | - |
| `image72` | `string \| null \| undefined` | Optional | - |
| `imageOriginal` | `string \| null \| undefined` | Optional | - |
| `isAppUser` | `boolean \| undefined` | Optional | - |
| `isCustomImage` | `boolean \| undefined` | Optional | - |
| `isRestricted` | `boolean \| null \| undefined` | Optional | - |
| `isUltraRestricted` | `boolean \| null \| undefined` | Optional | - |
| `lastAvatarImageHash` | `string \| undefined` | Optional | - |
| `lastName` | `string \| null \| undefined` | Optional | - |
| `membershipsCount` | `number \| undefined` | Optional | - |
| `name` | `string \| null \| undefined` | Optional | - |
| `phone` | `string` | Required | - |
| `pronouns` | `string \| undefined` | Optional | - |
| `realName` | `string` | Required | - |
| `realNameNormalized` | `string` | Required | - |
| `skype` | `string` | Required | - |
| `statusDefaultEmoji` | `string \| undefined` | Optional | - |
| `statusDefaultText` | `string \| undefined` | Optional | - |
| `statusDefaultTextCanonical` | `string \| null \| undefined` | Optional | - |
| `statusEmoji` | `string` | Required | - |
| `statusExpiration` | `number \| undefined` | Optional | - |
| `statusText` | `string` | Required | - |
| `statusTextCanonical` | `string \| null \| undefined` | Optional | - |
| `team` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `title` | `string` | Required | - |
| `updated` | `number \| undefined` | Optional | - |
| `userId` | `string \| undefined` | Optional | - |
| `username` | `string \| null \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "always_active": false,
  "api_app_id": "api_app_id8",
  "avatar_hash": "avatar_hash8",
  "bot_id": "bot_id8",
  "display_name": "display_name8",
  "display_name_normalized": "display_name_normalized8",
  "email": "email8",
  "fields": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "first_name": "first_name8",
  "phone": "phone2",
  "real_name": "real_name6",
  "real_name_normalized": "real_name_normalized8",
  "skype": "skype8",
  "status_emoji": "status_emoji2",
  "status_text": "status_text0",
  "title": "title4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

