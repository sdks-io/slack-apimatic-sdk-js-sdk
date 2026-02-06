
# Api Method Users Get Presence

Generated from users.getPresence with shasum e7251aec575d8863f9e0eb38663ae9dc26655f65

*This model accepts additional fields of type unknown.*

## Structure

`ApiMethodUsersGetPresence`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `autoAway` | `boolean \| undefined` | Optional | - |
| `connectionCount` | `number \| undefined` | Optional | - |
| `lastActivity` | `number \| undefined` | Optional | - |
| `manualAway` | `boolean \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `online` | `boolean \| undefined` | Optional | - |
| `presence` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "True",
  "presence": "presence8",
  "auto_away": false,
  "connection_count": 42,
  "last_activity": 166,
  "manual_away": false,
  "online": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

