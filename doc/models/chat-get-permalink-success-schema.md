
# Chat Get Permalink Success Schema

Schema for successful response chat.getPermalink

*This model accepts additional fields of type unknown.*

## Structure

`ChatGetPermalinkSuccessSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `string` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `permalink` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "channel": "channel8",
  "ok": "True",
  "permalink": "permalink4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

