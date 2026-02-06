
# Objs Team Profile Field Option

*This model accepts additional fields of type unknown.*

## Structure

`ObjsTeamProfileFieldOption`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `isCustom` | `boolean \| null \| undefined` | Optional | - |
| `isMultipleEntry` | `boolean \| null \| undefined` | Optional | - |
| `isProtected` | `boolean \| null \| undefined` | Optional | - |
| `isScim` | `boolean \| null \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "is_custom": false,
  "is_multiple_entry": false,
  "is_protected": false,
  "is_scim": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

