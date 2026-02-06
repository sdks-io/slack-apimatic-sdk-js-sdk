
# Rtm Connect Schema

Schema for successful response from rtm.connect method

*This model accepts additional fields of type unknown.*

## Structure

`RtmConnectSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `self` | [`Self`](../../doc/models/self.md) | Required | - |
| `team` | [`Team1`](../../doc/models/team-1.md) | Required | - |
| `url` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "self": {
    "id": "id8",
    "name": "name8",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "team": {
    "domain": "domain6",
    "id": "id0",
    "name": "name0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "url": "url8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

