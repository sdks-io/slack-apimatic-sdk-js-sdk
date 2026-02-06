
# Log

*This model accepts additional fields of type unknown.*

## Structure

`Log`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `adminAppId` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `appId` | `string` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` |
| `appType` | `string` | Required | - |
| `changeType` | `string` | Required | - |
| `channel` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` |
| `date` | `string` | Required | - |
| `scope` | `string` | Required | - |
| `serviceId` | `string \| undefined` | Optional | - |
| `serviceType` | `string \| undefined` | Optional | - |
| `userId` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `userName` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "admin_app_id": "admin_app_id2",
  "app_id": "app_id2",
  "app_type": "app_type8",
  "change_type": "change_type2",
  "channel": "channel0",
  "date": "date0",
  "scope": "scope8",
  "service_id": "service_id6",
  "service_type": "service_type0",
  "user_id": "user_id2",
  "user_name": "user_name0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

