# Apps

```ts
const appsApi = new AppsApi(client);
```

## Class Name

`AppsApi`


# Apps Uninstall

Uninstalls your app from a workspace.

API method documentation: [https://api.slack.com/methods/apps.uninstall](https://api.slack.com/methods/apps.uninstall)

```ts
async appsUninstall(
  token?: string,
  clientId?: string,
  clientSecret?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AppsUninstallSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `none` |
| `clientId` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AppsUninstallSchema`](../../doc/models/apps-uninstall-schema.md).

## Example Usage

```ts
try {
  const response = await appsApi.appsUninstall();

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
    if (error instanceof AppsUninstallErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AppsUninstallErrorSchemaError`](../../doc/models/apps-uninstall-error-schema-error.md) |

