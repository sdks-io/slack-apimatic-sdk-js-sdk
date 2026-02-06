
# Paging Object

*This model accepts additional fields of type unknown.*

## Structure

`PagingObject`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `count` | `number \| undefined` | Optional | - |
| `page` | `number` | Required | - |
| `pages` | `number \| undefined` | Optional | - |
| `perPage` | `number \| undefined` | Optional | - |
| `spill` | `number \| undefined` | Optional | - |
| `total` | `number` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "count": 190,
  "page": 160,
  "pages": 28,
  "per_page": 72,
  "spill": 132,
  "total": 140,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

