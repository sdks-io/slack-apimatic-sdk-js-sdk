
# File Comment Object

*This model accepts additional fields of type unknown.*

## Structure

`FileCommentObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `comment` | `string` | Required | - |
| `created` | `number` | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^Fc[A-Z0-9]{8,}$` |
| `isIntro` | `boolean` | Required | - |
| `isStarred` | `boolean \| undefined` | Optional | - |
| `numStars` | `number \| undefined` | Optional | - |
| `pinnedInfo` | `unknown \| undefined` | Optional | - |
| `pinnedTo` | `string[] \| undefined` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `reactions` | [`ReactionObject[] \| undefined`](../../doc/models/reaction-object.md) | Optional | - |
| `timestamp` | `number` | Required | - |
| `user` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "comment": "comment2",
  "created": 212,
  "id": "id4",
  "is_intro": false,
  "is_starred": false,
  "num_stars": 180,
  "pinned_info": {
    "key1": "val1",
    "key2": "val2"
  },
  "pinned_to": [
    "pinned_to8",
    "pinned_to9"
  ],
  "reactions": [
    {
      "count": 208,
      "name": "name8",
      "users": [
        "users5",
        "users6",
        "users7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "count": 208,
      "name": "name8",
      "users": [
        "users5",
        "users6",
        "users7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "timestamp": 66,
  "user": "user4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

