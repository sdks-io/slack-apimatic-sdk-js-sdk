
# Purpose

*This model accepts additional fields of type unknown.*

## Structure

`Purpose`

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
  "creator": "creator6",
  "last_set": 108,
  "value": "value0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

