
# Team 1

*This model accepts additional fields of type unknown.*

## Structure

`Team1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `domain` | `string` | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` |
| `name` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "domain": "domain0",
  "id": "id4",
  "name": "name4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

