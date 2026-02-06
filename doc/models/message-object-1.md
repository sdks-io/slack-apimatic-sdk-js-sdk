
# Message Object 1

*This model accepts additional fields of type unknown.*

## Structure

`MessageObject1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `attachments` | `unknown[] \| undefined` | Optional | - |
| `blocks` | `unknown \| undefined` | Optional | - |
| `text` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "attachments": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "blocks": {
    "key1": "val1",
    "key2": "val2"
  },
  "text": "text4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

