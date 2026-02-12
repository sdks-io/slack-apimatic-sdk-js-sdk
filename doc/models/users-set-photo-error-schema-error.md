
# Users Set Photo Error Schema Error

Schema for error response from users.setPhoto method

*This model accepts additional fields of type unknown.*

## Structure

`UsersSetPhotoErrorSchemaError`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `debugStep` | `string \| undefined` | Optional | possibly DEV/QA only |
| `dims` | `string \| undefined` | Optional | possibly DEV/QA only |
| `error` | [`UsersSetPhotoErrorEnum`](../../doc/models/users-set-photo-error-enum.md) | Required | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `timeIdent` | `number \| undefined` | Optional | possibly DEV/QA only |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "error": "account_inactive",
  "ok": "False",
  "callstack": "callstack4",
  "debug_step": "debug_step0",
  "dims": "dims8",
  "time_ident": 18,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

