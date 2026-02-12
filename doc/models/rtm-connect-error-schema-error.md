
# Rtm Connect Error Schema Error

Schema for error response from rtm.connect method

*This model accepts additional fields of type unknown.*

## Structure

`RtmConnectErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`RtmConnectErrorEnum`](../../doc/models/rtm-connect-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "invalid_arg_name",
  "ok": "False",
  "callstack": "callstack2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

