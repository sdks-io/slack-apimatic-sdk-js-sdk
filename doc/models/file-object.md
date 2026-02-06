
# File Object

*This model accepts additional fields of type unknown.*

## Structure

`FileObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channels` | `string[] \| undefined` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `commentsCount` | `number \| undefined` | Optional | - |
| `created` | `number \| undefined` | Optional | - |
| `dateDelete` | `number \| undefined` | Optional | - |
| `displayAsBot` | `boolean \| undefined` | Optional | - |
| `editable` | `boolean \| undefined` | Optional | - |
| `editor` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `externalId` | `string \| undefined` | Optional | - |
| `externalType` | `string \| undefined` | Optional | - |
| `externalUrl` | `string \| undefined` | Optional | - |
| `filetype` | `string \| undefined` | Optional | - |
| `groups` | `string[] \| undefined` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[G][A-Z0-9]{8,}$` |
| `hasRichPreview` | `boolean \| undefined` | Optional | - |
| `id` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[F][A-Z0-9]{8,}$` |
| `imageExifRotation` | `number \| undefined` | Optional | - |
| `ims` | `string[] \| undefined` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[D][A-Z0-9]{8,}$` |
| `isExternal` | `boolean \| undefined` | Optional | - |
| `isPublic` | `boolean \| undefined` | Optional | - |
| `isStarred` | `boolean \| undefined` | Optional | - |
| `isTombstoned` | `boolean \| undefined` | Optional | - |
| `lastEditor` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `mimetype` | `string \| undefined` | Optional | - |
| `mode` | `string \| undefined` | Optional | - |
| `name` | `string \| undefined` | Optional | - |
| `nonOwnerEditable` | `boolean \| undefined` | Optional | - |
| `numStars` | `number \| undefined` | Optional | - |
| `originalH` | `number \| undefined` | Optional | - |
| `originalW` | `number \| undefined` | Optional | - |
| `permalink` | `string \| undefined` | Optional | - |
| `permalinkPublic` | `string \| undefined` | Optional | - |
| `pinnedInfo` | `unknown \| undefined` | Optional | - |
| `pinnedTo` | `string[] \| undefined` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `prettyType` | `string \| undefined` | Optional | - |
| `preview` | `string \| undefined` | Optional | - |
| `publicUrlShared` | `boolean \| undefined` | Optional | - |
| `reactions` | [`ReactionObject[] \| undefined`](../../doc/models/reaction-object.md) | Optional | - |
| `shares` | [`Shares \| undefined`](../../doc/models/shares.md) | Optional | - |
| `size` | `number \| undefined` | Optional | - |
| `sourceTeam` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `state` | `string \| undefined` | Optional | - |
| `thumb1024` | `string \| undefined` | Optional | - |
| `thumb1024H` | `number \| undefined` | Optional | - |
| `thumb1024W` | `number \| undefined` | Optional | - |
| `thumb160` | `string \| undefined` | Optional | - |
| `thumb360` | `string \| undefined` | Optional | - |
| `thumb360H` | `number \| undefined` | Optional | - |
| `thumb360W` | `number \| undefined` | Optional | - |
| `thumb480` | `string \| undefined` | Optional | - |
| `thumb480H` | `number \| undefined` | Optional | - |
| `thumb480W` | `number \| undefined` | Optional | - |
| `thumb64` | `string \| undefined` | Optional | - |
| `thumb720` | `string \| undefined` | Optional | - |
| `thumb720H` | `number \| undefined` | Optional | - |
| `thumb720W` | `number \| undefined` | Optional | - |
| `thumb80` | `string \| undefined` | Optional | - |
| `thumb800` | `string \| undefined` | Optional | - |
| `thumb800H` | `number \| undefined` | Optional | - |
| `thumb800W` | `number \| undefined` | Optional | - |
| `thumb960` | `string \| undefined` | Optional | - |
| `thumb960H` | `number \| undefined` | Optional | - |
| `thumb960W` | `number \| undefined` | Optional | - |
| `thumbTiny` | `string \| undefined` | Optional | - |
| `timestamp` | `number \| undefined` | Optional | - |
| `title` | `string \| undefined` | Optional | - |
| `updated` | `number \| undefined` | Optional | - |
| `urlPrivate` | `string \| undefined` | Optional | - |
| `urlPrivateDownload` | `string \| undefined` | Optional | - |
| `user` | `string \| undefined` | Optional | - |
| `userTeam` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `username` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels2",
    "channels1"
  ],
  "comments_count": 94,
  "created": 2,
  "date_delete": 156,
  "display_as_bot": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

