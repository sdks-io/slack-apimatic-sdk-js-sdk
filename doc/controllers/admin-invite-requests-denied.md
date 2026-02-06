# Admin Invite Requests Denied

```ts
const adminInviteRequestsDeniedApi = new AdminInviteRequestsDeniedApi(client);
```

## Class Name

`AdminInviteRequestsDeniedApi`


# Admin Invite Requests Denied List

List all denied workspace invite requests.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.denied.list](https://api.slack.com/methods/admin.inviteRequests.denied.list)

```ts
async adminInviteRequestsDeniedList(
  token: string,
  teamId?: string,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.invites:read` |
| `teamId` | `string \| undefined` | Query, Optional | ID for the workspace where the invite requests were made. |
| `cursor` | `string \| undefined` | Query, Optional | Value of the `next_cursor` field sent as part of the previous api response |
| `limit` | `number \| undefined` | Query, Optional | The number of results that will be returned by the API on each invocation. Must be between 1 - 1000 both inclusive |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.invites:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await adminInviteRequestsDeniedApi.adminInviteRequestsDeniedList(token);

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
    if (error instanceof DefaultErrorTemplateError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |

