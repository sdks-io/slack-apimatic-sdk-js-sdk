# Apps Permissions

```ts
const appsPermissionsApi = new AppsPermissionsApi(client);
```

## Class Name

`AppsPermissionsApi`

## Methods

* [Apps Permissions Info](../../doc/controllers/apps-permissions.md#apps-permissions-info)
* [Apps Permissions Request](../../doc/controllers/apps-permissions.md#apps-permissions-request)


# Apps Permissions Info

Returns list of permissions this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.info](https://api.slack.com/methods/apps.permissions.info)

```ts
async appsPermissionsInfo(
  token?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AppsPermissionsInfoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `none` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AppsPermissionsInfoSchema`](../../doc/models/apps-permissions-info-schema.md).

## Example Usage

```ts
try {
  const response = await appsPermissionsApi.appsPermissionsInfo();

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
    if (error instanceof AppsPermissionsInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`AppsPermissionsInfoErrorSchemaError`](../../doc/models/apps-permissions-info-error-schema-error.md) |


# Apps Permissions Request

Allows an app to request additional scopes

API method documentation: [https://api.slack.com/methods/apps.permissions.request](https://api.slack.com/methods/apps.permissions.request)

```ts
async appsPermissionsRequest(
  token: string,
  scopes: string,
  triggerId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AppsPermissionsRequestSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `scopes` | `string` | Query, Required | A comma separated list of scopes to request for |
| `triggerId` | `string` | Query, Required | Token used to trigger the permissions API |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AppsPermissionsRequestSchema`](../../doc/models/apps-permissions-request-schema.md).

## Example Usage

```ts
const token = 'token6';

const scopes = 'scopes4';

const triggerId = 'trigger_id6';

try {
  const response = await appsPermissionsApi.appsPermissionsRequest(
    token,
    scopes,
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
    if (error instanceof AppsPermissionsRequestErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when trigger_id is invalid | [`AppsPermissionsRequestErrorSchemaError`](../../doc/models/apps-permissions-request-error-schema-error.md) |

