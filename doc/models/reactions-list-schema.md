
# Reactions List Schema

Schema for successful response from reactions.list method

*This model accepts additional fields of type unknown.*

## Structure

`ReactionsListSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `items` | `unknown[]` | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `paging` | [`PagingObject \| undefined`](../../doc/models/paging-object.md) | Optional | - |
| `responseMetadata` | `unknown \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "items": [
    {
      "key1": "val1",
      "key2": "val2"
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
  "response_metadata": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

