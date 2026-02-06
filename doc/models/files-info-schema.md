
# Files Info Schema

Schema for successful response from files.info method

*This model accepts additional fields of type unknown.*

## Structure

`FilesInfoSchema`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `comments` | `unknown[]` | Required | - |
| `contentHtml` | `string \| null \| undefined` | Optional | - |
| `editor` | `string \| undefined` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` |
| `file` | [`FileObject`](../../doc/models/file-object.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'True'` |
| `paging` | [`PagingObject \| undefined`](../../doc/models/paging-object.md) | Optional | - |
| `responseMetadata` | `unknown \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "comments": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "file": {
    "channels": [
      "channels5",
      "channels4"
    ],
    "comments_count": 56,
    "created": 220,
    "date_delete": 118,
    "display_as_bot": false,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "content_html": "content_html0",
  "editor": "editor6",
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

