
# Resources in Info From Apps Permissions Info

*This model accepts additional fields of type unknown.*

## Structure

`ResourcesInInfoFromAppsPermissionsInfo`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `excludedIds` | `unknown[] \| undefined` | Optional | - |
| `ids` | `unknown[]` | Required | - |
| `wildcard` | `boolean \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "excluded_ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "wildcard": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

