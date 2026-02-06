# Admin Invite Requests

```ts
const adminInviteRequestsApi = new AdminInviteRequestsApi(client);
```

## Class Name

`AdminInviteRequestsApi`

## Methods

* [Admin Invite Requests Approve](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-approve)
* [Admin Invite Requests Deny](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-deny)
* [Admin Invite Requests List](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-list)


# Admin Invite Requests Approve

Approve a workspace invite request.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.approve](https://api.slack.com/methods/admin.inviteRequests.approve)

```ts
async adminInviteRequestsApprove(
  token: string,
  inviteRequestId: string,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.invites:write` |
| `inviteRequestId` | `string` | Form, Required | ID of the request to invite. |
| `teamId` | `string \| undefined` | Form, Optional | ID for the workspace where the invite request was made. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.invites:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const inviteRequestId = 'invite_request_id4';

try {
  const response = await adminInviteRequestsApi.adminInviteRequestsApprove(
    token,
    inviteRequestId
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


# Admin Invite Requests Deny

Deny a workspace invite request.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.deny](https://api.slack.com/methods/admin.inviteRequests.deny)

```ts
async adminInviteRequestsDeny(
  token: string,
  inviteRequestId: string,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.invites:write` |
| `inviteRequestId` | `string` | Form, Required | ID of the request to invite. |
| `teamId` | `string \| undefined` | Form, Optional | ID for the workspace where the invite request was made. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.invites:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const inviteRequestId = 'invite_request_id4';

try {
  const response = await adminInviteRequestsApi.adminInviteRequestsDeny(
    token,
    inviteRequestId
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


# Admin Invite Requests List

List all pending workspace invite requests.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.list](https://api.slack.com/methods/admin.inviteRequests.list)

```ts
async adminInviteRequestsList(
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
| `cursor` | `string \| undefined` | Query, Optional | Value of the `next_cursor` field sent as part of the previous API response |
| `limit` | `number \| undefined` | Query, Optional | The number of results that will be returned by the API on each invocation. Must be between 1 - 1000, both inclusive |
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
  const response = await adminInviteRequestsApi.adminInviteRequestsList(token);

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

