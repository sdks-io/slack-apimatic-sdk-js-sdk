# Admin Users Session

```ts
const adminUsersSessionApi = new AdminUsersSessionApi(client);
```

## Class Name

`AdminUsersSessionApi`

## Methods

* [Admin Users Session Invalidate](../../doc/controllers/admin-users-session.md#admin-users-session-invalidate)
* [Admin Users Session Reset](../../doc/controllers/admin-users-session.md#admin-users-session-reset)


# Admin Users Session Invalidate

Invalidate a single session for a user by session_id

API method documentation: [https://api.slack.com/methods/admin.users.session.invalidate](https://api.slack.com/methods/admin.users.session.invalidate)

```ts
async adminUsersSessionInvalidate(
  token: string,
  teamId: string,
  sessionId: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `string` | Form, Required | ID of the team that the session belongs to |
| `sessionId` | `number` | Form, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamId = 'team_id6';

const sessionId = 2;

try {
  const response = await adminUsersSessionApi.adminUsersSessionInvalidate(
    token,
    teamId,
    sessionId
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


# Admin Users Session Reset

Wipes all valid sessions on all devices for a given user

API method documentation: [https://api.slack.com/methods/admin.users.session.reset](https://api.slack.com/methods/admin.users.session.reset)

```ts
async adminUsersSessionReset(
  token: string,
  userId: string,
  mobileOnly?: boolean,
  webOnly?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `userId` | `string` | Form, Required | The ID of the user to wipe sessions for |
| `mobileOnly` | `boolean \| undefined` | Form, Optional | Only expire mobile sessions (default: false) |
| `webOnly` | `boolean \| undefined` | Form, Optional | Only expire web sessions (default: false) |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const userId = 'user_id8';

try {
  const response = await adminUsersSessionApi.adminUsersSessionReset(
    token,
    userId
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

