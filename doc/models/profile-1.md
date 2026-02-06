
# Profile 1

*This model accepts additional fields of type unknown.*

## Structure

`Profile1`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `avatarHash` | `string` | Required | **Constraints**: *Pattern*: `^[0-9a-f]{12}$` |
| `image1024` | `string` | Required | - |
| `image192` | `string` | Required | - |
| `image24` | `string` | Required | - |
| `image32` | `string` | Required | - |
| `image48` | `string` | Required | - |
| `image512` | `string` | Required | - |
| `image72` | `string` | Required | - |
| `imageOriginal` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash6",
  "image_1024": "image_10242",
  "image_192": "image_1922",
  "image_24": "image_242",
  "image_32": "image_322",
  "image_48": "image_484",
  "image_512": "image_5128",
  "image_72": "image_720",
  "image_original": "image_original2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

