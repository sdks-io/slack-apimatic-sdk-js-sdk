
# Scopes

*This model accepts additional fields of type unknown.*

## Structure

`Scopes`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `appHome` | `string[] \| undefined` | Optional | - |
| `channel` | `string[] \| undefined` | Optional | - |
| `group` | `string[] \| undefined` | Optional | - |
| `im` | `string[] \| undefined` | Optional | - |
| `mpim` | `string[] \| undefined` | Optional | - |
| `team` | `string[] \| undefined` | Optional | - |
| `user` | `string[] \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "app_home": [
    "app_home2",
    "app_home1",
    "app_home0"
  ],
  "channel": [
    "channel0",
    "channel9"
  ],
  "group": [
    "group9"
  ],
  "im": [
    "im1",
    "im0",
    "im9"
  ],
  "mpim": [
    "mpim0"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

