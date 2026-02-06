
# Attachment

*This model accepts additional fields of type unknown.*

## Structure

`Attachment`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `fallback` | `string \| undefined` | Optional | - |
| `id` | `number` | Required | - |
| `imageBytes` | `number \| undefined` | Optional | - |
| `imageHeight` | `number \| undefined` | Optional | - |
| `imageUrl` | `string \| undefined` | Optional | - |
| `imageWidth` | `number \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "fallback": "fallback4",
  "id": 158,
  "image_bytes": 168,
  "image_height": 20,
  "image_url": "image_url6",
  "image_width": 146,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

