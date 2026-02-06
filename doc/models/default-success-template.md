
# Default Success Template

This method either only returns a brief _OK_ response or a verbose schema is not available for this method.

*This model accepts additional fields of type unknown.*

## Structure

`DefaultSuccessTemplate`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

