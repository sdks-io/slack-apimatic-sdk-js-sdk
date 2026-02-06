
# Icons

*This model accepts additional fields of type unknown.*

## Structure

`Icons`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `image36` | `string` | Required | - |
| `image48` | `string` | Required | - |
| `image72` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "image_36": "image_360",
  "image_48": "image_480",
  "image_72": "image_726",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

