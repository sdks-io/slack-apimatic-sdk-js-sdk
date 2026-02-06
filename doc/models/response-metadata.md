
# Response Metadata

*This model accepts additional fields of type unknown.*

## Structure

`ResponseMetadata`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `nextCursor` | `string` | Required | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "next_cursor": "next_cursor0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

