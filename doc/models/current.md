
# Current

*This model accepts additional fields of type unknown.*

## Structure

`Current`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `dateStarted` | `number` | Required | - |
| `teamId` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "date_started": 30,
  "team_id": "team_id4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

