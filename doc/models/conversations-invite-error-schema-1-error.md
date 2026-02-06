
# Conversations Invite Error Schema 1 Error

Schema for error response from conversations.invite method

*This model accepts additional fields of type unknown.*

## Structure

`ConversationsInviteErrorSchema1Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `callstack` | `string \| undefined` | Optional | Note: PHP callstack is only visible in dev/qa |
| `error` | [`Error35 \| undefined`](../../doc/models/error-35.md) | Optional | - |
| `errors` | [`ErrorsIsReturnedWhenAnErrorAssociatesAnUser[] \| undefined`](../../doc/models/errors-is-returned-when-an-error-associates-an-user.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* |
| `needed` | `string \| undefined` | Optional | - |
| `ok` | `string` | Required, Constant | **Value**: `'False'` |
| `provided` | `string \| undefined` | Optional | - |
| `additionalProperties` | `Record<string, unknown>` | Optional | - |

## Example (as JSON)

```json
{
  "ok": "False",
  "callstack": "callstack2",
  "error": "invalid_post_type",
  "errors": [
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "needed": "needed6",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

