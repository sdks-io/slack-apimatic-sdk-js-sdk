
# Prefs

*This model accepts additional fields of type unknown.*

## Structure

`Prefs`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channels` | `string[]` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` |
| `groups` | `string[]` | Required | **Constraints**: *Pattern*: `^[G][A-Z0-9]{8,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels4",
    "channels5"
  ],
  "groups": [
    "groups6",
    "groups7"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

