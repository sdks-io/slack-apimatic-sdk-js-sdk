
# Topic

*This model accepts additional fields of type unknown.*

## Structure

`Topic`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `creator` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{8,}$\|^$` |
| `lastSet` | `number` | Required | - |
| `value` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "creator": "creator8",
  "last_set": 254,
  "value": "value2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

