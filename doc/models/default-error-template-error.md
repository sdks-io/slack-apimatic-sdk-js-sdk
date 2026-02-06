
# Default Error Template Error

This method either only returns a brief _not OK_ response or a verbose schema is not available for this method.

*This model accepts additional fields of type unknown.*

## Structure

`DefaultErrorTemplateError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

