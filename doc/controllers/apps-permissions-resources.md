# Apps Permissions Resources

```ts
const appsPermissionsResourcesApi = new AppsPermissionsResourcesApi(client);
```

## Class Name

`AppsPermissionsResourcesApi`


# Apps Permissions Resources List

Returns list of resource grants this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.resources.list](https://api.slack.com/methods/apps.permissions.resources.list)

```ts
async appsPermissionsResourcesList(
  token: string,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AppsPermissionsResourcesListSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AppsPermissionsResourcesListSuccessSchema`](../../doc/models/apps-permissions-resources-list-success-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await appsPermissionsResourcesApi.appsPermissionsResourcesList(token);

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
    if (error instanceof AppsPermissionsResourcesListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsPermissionsResourcesListErrorSchemaError`](../../doc/models/apps-permissions-resources-list-error-schema-error.md) |

