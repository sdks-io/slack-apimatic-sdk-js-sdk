# Apps Permissions Users

```ts
const appsPermissionsUsersApi = new AppsPermissionsUsersApi(client);
```

## Class Name

`AppsPermissionsUsersApi`

## Methods

* [Apps Permissions Users List](../../doc/controllers/apps-permissions-users.md#apps-permissions-users-list)
* [Apps Permissions Users Request](../../doc/controllers/apps-permissions-users.md#apps-permissions-users-request)


# Apps Permissions Users List

Returns list of user grants and corresponding scopes this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.users.list](https://api.slack.com/methods/apps.permissions.users.list)

```ts
async appsPermissionsUsersList(
  token: string,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await appsPermissionsUsersApi.appsPermissionsUsersList(token);

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


# Apps Permissions Users Request

Enables an app to trigger a permissions modal to grant an app access to a user access scope.

API method documentation: [https://api.slack.com/methods/apps.permissions.users.request](https://api.slack.com/methods/apps.permissions.users.request)

```ts
async appsPermissionsUsersRequest(
  token: string,
  scopes: string,
  triggerId: string,
  user: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `scopes` | `string` | Query, Required | A comma separated list of user scopes to request for |
| `triggerId` | `string` | Query, Required | Token used to trigger the request |
| `user` | `string` | Query, Required | The user this scope is being requested for |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const scopes = 'scopes4';

const triggerId = 'trigger_id6';

const user = 'user0';

try {
  const response = await appsPermissionsUsersApi.appsPermissionsUsersRequest(
    token,
    scopes,
    triggerId,
    user
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
| Default | Standard failure response when trigger_id is invalid | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |

