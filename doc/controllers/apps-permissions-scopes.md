# Apps Permissions Scopes

```ts
const appsPermissionsScopesApi = new AppsPermissionsScopesApi(client);
```

## Class Name

`AppsPermissionsScopesApi`


# Apps Permissions Scopes List

Returns list of scopes this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.scopes.list](https://api.slack.com/methods/apps.permissions.scopes.list)

```ts
async appsPermissionsScopesList(
  token: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ApiPermissionsScopesListSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ApiPermissionsScopesListSuccessSchema`](../../doc/models/api-permissions-scopes-list-success-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await appsPermissionsScopesApi.appsPermissionsScopesList(token);

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
    if (error instanceof AppsPermissionsScopesListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsPermissionsScopesListErrorSchemaError`](../../doc/models/apps-permissions-scopes-list-error-schema-error.md) |

