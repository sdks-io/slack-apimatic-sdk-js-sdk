
# Errors Is Returned When an Error Associates an User

*This model accepts additional fields of type unknown.*

## Structure

`ErrorsIsReturnedWhenAnErrorAssociatesAnUser`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | [`Error35`](../../doc/models/error-35.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `user` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "cant_invite",
  "ok": "False",
  "user": "user8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

