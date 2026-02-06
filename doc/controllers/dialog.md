# Dialog

```ts
const dialogApi = new DialogApi(client);
```

## Class Name

`DialogApi`


# Dialog Open

Open a dialog with a user

API method documentation: [https://api.slack.com/methods/dialog.open](https://api.slack.com/methods/dialog.open)

```ts
async dialogOpen(
  token: string,
  dialog: string,
  triggerId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DialogOpenSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `dialog` | `string` | Query, Required | The dialog definition. This must be a JSON-encoded string. |
| `triggerId` | `string` | Query, Required | Exchange a trigger to post to the user. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DialogOpenSchema`](../../doc/models/dialog-open-schema.md).

## Example Usage

```ts
const token = 'token6';

const dialog = 'dialog4';

const triggerId = 'trigger_id6';

try {
  const response = await dialogApi.dialogOpen(
    token,
    dialog,
    triggerId
  );

  // Extracting fully parsed response body.
  console.log(response.result);

  // Extracting response status code.
  console.log(response.statusCode);
  // Extracting response headers.
  console.log(response.headers);
  // Extracting response body of type `string | Stream`
  console.log(response.body);
} catch (error) {
  if (error instanceof ApiError) {
    // Extracting response error status code.
    console.log(error.statusCode);
    // Extracting response error headers.
    console.log(error.headers);
    // Extracting response error body of type `string | Stream`.
    console.log(error.body);
    if (error instanceof DialogOpenErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response, before getting to any possible validation errors. | [`DialogOpenErrorSchemaError`](../../doc/models/dialog-open-error-schema-error.md) |

