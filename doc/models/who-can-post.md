
# Who Can Post

*This model accepts additional fields of type unknown.*

## Structure

`WhoCanPost`

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
    "type7",
    "type8"
  ],
  "user": [
    "user8",
    "user9"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

