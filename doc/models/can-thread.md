
# Can Thread

*This model accepts additional fields of type unknown.*

## Structure

`CanThread`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `type` | `string[] \| undefined` | Optional | - |
| `user` | `string[] \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "type": [
    "type7"
  ],
  "user": [
    "user2",
    "user3",
    "user4"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

