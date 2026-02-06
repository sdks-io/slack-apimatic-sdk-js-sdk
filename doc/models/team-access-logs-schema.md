
# Team Access Logs Schema

Schema for successful response from team.accessLogs method

*This model accepts additional fields of type unknown.*

## Structure

`TeamAccessLogsSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `logins` | [`Login[]`](../../doc/models/login.md) | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `paging` | [`PagingObject`](../../doc/models/paging-object.md) | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "logins": [
    {
      "count": 244,
      "country": "country8",
      "date_first": 108,
      "date_last": 124,
      "ip": "ip8",
      "isp": "isp4",
      "region": "region0",
      "user_agent": "user_agent6",
      "user_id": "user_id2",
      "username": "username6",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "ok": "True",
  "paging": {
    "count": 56,
    "page": 26,
    "pages": 150,
    "per_page": 194,
    "spill": 246,
    "total": 6,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

