
# Bot

*This model accepts additional fields of type unknown.*

## Structure

`Bot`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `appId` | `string` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `deleted` | `boolean` | Required | - |
| `icons` | [`Icons`](../../doc/models/icons.md) | Required | - |
| `id` | `string` | Required | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` |
| `name` | `string` | Required | - |
| `updated` | `number` | Required | - |
| `userId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "app_id": "app_id2",
  "deleted": false,
  "icons": {
    "image_36": "image_362",
    "image_48": "image_488",
    "image_72": "image_722",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "id": "id4",
  "name": "name4",
  "updated": 186,
  "user_id": "user_id2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

