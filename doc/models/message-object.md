
# Message Object

*This model accepts additional fields of type unknown.*

## Structure

`MessageObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `attachments` | [`Attachment[] \| undefined`](../../doc/models/attachment.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `blocks` | [`BlockKitBlock[] \| undefined`](../../doc/models/block-kit-block.md) | Optional | This is a very loose definition, in the future, we'll populate this with deeper schema in this definition namespace. |
| `botId` | `unknown \| undefined` | Optional | - |
| `botProfile` | [`BotProfileObject \| undefined`](../../doc/models/bot-profile-object.md) | Optional | - |
| `clientMsgId` | `string \| undefined` | Optional | - |
| `comment` | [`FileCommentObject \| undefined`](../../doc/models/file-comment-object.md) | Optional | - |
| `displayAsBot` | `boolean \| undefined` | Optional | - |
| `file` | [`FileObject \| undefined`](../../doc/models/file-object.md) | Optional | - |
| `files` | [`FileObject[] \| undefined`](../../doc/models/file-object.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `icons` | [`Icons1 \| undefined`](../../doc/models/icons-1.md) | Optional | - |
| `inviter` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `isDelayedMessage` | `boolean \| undefined` | Optional | - |
| `isIntro` | `boolean \| undefined` | Optional | - |
| `isStarred` | `boolean \| undefined` | Optional | - |
| `lastRead` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `latestReply` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `name` | `string \| undefined` | Optional | - |
| `oldName` | `string \| undefined` | Optional | - |
| `parentUserId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `permalink` | `string \| undefined` | Optional | - |
| `pinnedTo` | `string[] \| undefined` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `purpose` | `string \| undefined` | Optional | - |
| `reactions` | [`ReactionObject[] \| undefined`](../../doc/models/reaction-object.md) | Optional | - |
| `replyCount` | `number \| undefined` | Optional | - |
| `replyUsers` | `string[] \| undefined` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `replyUsersCount` | `number \| undefined` | Optional | - |
| `sourceTeam` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `subscribed` | `boolean \| undefined` | Optional | - |
| `subtype` | `string \| undefined` | Optional | - |
| `team` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `text` | `string` | Required | - |
| `threadTs` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `topic` | `string \| undefined` | Optional | - |
| `ts` | `string` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` |
| `type` | `string` | Required | - |
| `unreadCount` | `number \| undefined` | Optional | - |
| `upload` | `boolean \| undefined` | Optional | - |
| `user` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `userProfile` | [`ObjsUserProfileShort \| undefined`](../../doc/models/objs-user-profile-short.md) | Optional | - |
| `userTeam` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` |
| `username` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "attachments": [
    {
      "fallback": "fallback4",
      "id": 36,
      "image_bytes": 34,
      "image_height": 154,
      "image_url": "image_url6",
      "image_width": 24,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "fallback": "fallback4",
      "id": 36,
      "image_bytes": 34,
      "image_height": 154,
      "image_url": "image_url6",
      "image_width": 24,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "blocks": [
    {
      "type": "type4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "type": "type4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "bot_id": {
    "key1": "val1",
    "key2": "val2"
  },
  "bot_profile": {
    "app_id": "app_id8",
    "deleted": false,
    "icons": {
      "image_36": "image_362",
      "image_48": "image_488",
      "image_72": "image_722",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "id": "id8",
    "name": "name8",
    "team_id": "team_id8",
    "updated": 44,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "client_msg_id": "client_msg_id4",
  "text": "text8",
  "ts": "ts0",
  "type": "type8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

