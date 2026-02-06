
# Shares

*This model accepts additional fields of type unknown.*

## Structure

`Shares`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `mPrivate` | `unknown \| undefined` | Optional | - |
| `mPublic` | `unknown \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "private": {
    "key1": "val1",
    "key2": "val2"
  },
  "public": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

