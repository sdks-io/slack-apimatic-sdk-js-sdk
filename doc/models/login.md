
# Login

*This model accepts additional fields of type unknown.*

## Structure

`Login`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `count` | `number` | Required | - |
| `country` | `string \| null` | Required | - |
| `dateFirst` | `number` | Required | - |
| `dateLast` | `number` | Required | - |
| `ip` | `string \| null` | Required | - |
| `isp` | `string \| null` | Required | - |
| `region` | `string \| null` | Required | - |
| `userAgent` | `string` | Required | - |
| `userId` | `string` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `username` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "count": 110,
  "country": "country6",
  "date_first": 14,
  "date_last": 2,
  "ip": "ip6",
  "isp": "isp2",
  "region": "region8",
  "user_agent": "user_agent4",
  "user_id": "user_id0",
  "username": "username8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

