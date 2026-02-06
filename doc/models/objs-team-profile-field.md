
# Objs Team Profile Field

*This model accepts additional fields of type unknown.*

## Structure

`ObjsTeamProfileField`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fieldName` | `string \| null \| undefined` | Optional | - |
| `hint` | `string` | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^X[a-zA-Z0-9]{9,}$` |
| `isHidden` | `boolean \| undefined` | Optional | - |
| `label` | `string` | Required | - |
| `options` | `unknown \| undefined` | Optional | - |
| `ordering` | `number` | Required | - |
| `possibleValues` | `string[] \| null \| undefined` | Optional | - |
| `type` | [`Type`](../../doc/models/type.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "field_name": "field_name4",
  "hint": "hint0",
  "id": "id0",
  "is_hidden": false,
  "label": "label0",
  "options": {
    "key1": "val1",
    "key2": "val2"
  },
  "ordering": 211.1,
  "possible_values": [
    "possible_values1",
    "possible_values2"
  ],
  "type": "options_list",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

