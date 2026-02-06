# Admin Apps

```ts
const adminAppsApi = new AdminAppsApi(client);
```

## Class Name

`AdminAppsApi`

## Methods

* [Admin Apps Approve](../../doc/controllers/admin-apps.md#admin-apps-approve)
* [Admin Apps Restrict](../../doc/controllers/admin-apps.md#admin-apps-restrict)


# Admin Apps Approve

Approve an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.approve](https://api.slack.com/methods/admin.apps.approve)

```ts
async adminAppsApprove(
  token: string,
  appId?: string,
  requestId?: string,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `appId` | `string \| undefined` | Form, Optional | The id of the app to approve. |
| `requestId` | `string \| undefined` | Form, Optional | The id of the request to approve. |
| `teamId` | `string \| undefined` | Form, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await adminAppsApi.adminAppsApprove(token);

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


# Admin Apps Restrict

Restrict an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.restrict](https://api.slack.com/methods/admin.apps.restrict)

```ts
async adminAppsRestrict(
  token: string,
  appId?: string,
  requestId?: string,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `appId` | `string \| undefined` | Form, Optional | The id of the app to restrict. |
| `requestId` | `string \| undefined` | Form, Optional | The id of the request to restrict. |
| `teamId` | `string \| undefined` | Form, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await adminAppsApi.adminAppsRestrict(token);

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

