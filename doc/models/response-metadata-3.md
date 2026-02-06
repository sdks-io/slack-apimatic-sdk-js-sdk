
# Response Metadata 3

*This model accepts additional fields of type unknown.*

## Structure

`ResponseMetadata3`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `warnings` | `string[] \| undefined` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "warnings": [
    "warnings4",
    "warnings5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

