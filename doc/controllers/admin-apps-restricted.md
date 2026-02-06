# Admin Apps Restricted

```ts
const adminAppsRestrictedApi = new AdminAppsRestrictedApi(client);
```

## Class Name

`AdminAppsRestrictedApi`


# Admin Apps Restricted List

List restricted apps for an org or workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.restricted.list](https://api.slack.com/methods/admin.apps.restricted.list)

```ts
async adminAppsRestrictedList(
  token: string,
  limit?: number,
  cursor?: string,
  teamId?: string,
  enterpriseId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.apps:read` |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `string \| undefined` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `teamId` | `string \| undefined` | Query, Optional | - |
| `enterpriseId` | `string \| undefined` | Query, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.apps:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await adminAppsRestrictedApi.adminAppsRestrictedList(token);

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

