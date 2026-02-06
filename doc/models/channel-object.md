
# Channel Object

*This model accepts additional fields of type unknown.*

## Structure

`ChannelObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `acceptedUser` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `created` | `number` | Required | - |
| `creator` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `isArchived` | `boolean \| undefined` | Optional | - |
| `isChannel` | `boolean` | Required | - |
| `isFrozen` | `boolean \| undefined` | Optional | - |
| `isGeneral` | `boolean \| undefined` | Optional | - |
| `isMember` | `boolean \| undefined` | Optional | - |
| `isMoved` | `number \| undefined` | Optional | - |
| `isMpim` | `boolean` | Required | - |
| `isNonThreadable` | `boolean \| undefined` | Optional | - |
| `isOrgShared` | `boolean` | Required | - |
| `isPendingExtShared` | `boolean \| undefined` | Optional | - |
| `isPrivate` | `boolean` | Required | - |
| `isReadOnly` | `boolean \| undefined` | Optional | - |
| `isShared` | `boolean` | Required | - |
| `isThreadOnly` | `boolean \| undefined` | Optional | - |
| `lastRead` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `latest` | `unknown \| undefined` | Optional | - |
| `members` | `string[]` | Required | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `name` | `string` | Required | - |
| `nameNormalized` | `string` | Required | - |
| `numMembers` | `number \| undefined` | Optional | - |
| `pendingShared` | `string[] \| undefined` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `previousNames` | `string[] \| undefined` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required* |
| `priority` | `number \| undefined` | Optional | - |
| `purpose` | [`Purpose`](../../doc/models/purpose.md) | Required | - |
| `topic` | [`Topic`](../../doc/models/topic.md) | Required | - |
| `unlinked` | `number \| undefined` | Optional | - |
| `unreadCount` | `number \| undefined` | Optional | - |
| `unreadCountDisplay` | `number \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "accepted_user": "accepted_user4",
  "created": 68,
  "creator": "creator4",
  "id": "id6",
  "is_archived": false,
  "is_channel": false,
  "is_frozen": false,
  "is_general": false,
  "is_member": false,
  "is_mpim": false,
  "is_org_shared": false,
  "is_private": false,
  "is_shared": false,
  "members": [
    "members4",
    "members5",
    "members6"
  ],
  "name": "name6",
  "name_normalized": "name_normalized4",
  "purpose": {
    "creator": "creator4",
    "last_set": 30,
    "value": "value8",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "topic": {
    "creator": "creator6",
    "last_set": 242,
    "value": "value0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

