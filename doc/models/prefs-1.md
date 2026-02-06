
# Prefs 1

*This model accepts additional fields of type unknown.*

## Structure

`Prefs1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `canThread` | [`CanThread \| undefined`](../../doc/models/can-thread.md) | Optional | - |
| `whoCanPost` | [`WhoCanPost \| undefined`](../../doc/models/who-can-post.md) | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "can_thread": {
    "type": [
      "type1",
      "type0"
    ],
    "user": [
      "user6",
      "user7"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "who_can_post": {
    "type": [
      "type5",
      "type4"
    ],
    "user": [
      "user0",
      "user1"
    ],
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

