
# Reaction Object

*This model accepts additional fields of type unknown.*

## Structure

`ReactionObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `count` | `number` | Required | - |
| `name` | `string` | Required | - |
| `users` | `string[]` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "count": 186,
  "name": "name6",
  "users": [
    "users3",
    "users2"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

