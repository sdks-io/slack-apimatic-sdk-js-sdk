# Apps Event Authorizations

```ts
const appsEventAuthorizationsApi = new AppsEventAuthorizationsApi(client);
```

## Class Name

`AppsEventAuthorizationsApi`


# Apps Event Authorizations List

Get a list of authorizations for the given event context. Each authorization represents an app installation that the event is visible to.

API method documentation: [https://api.slack.com/methods/apps.event.authorizations.list](https://api.slack.com/methods/apps.event.authorizations.list)

```ts
async appsEventAuthorizationsList(
  token: string,
  eventContext: string,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `authorizations:read` |
| `eventContext` | `string` | Query, Required | - |
| `cursor` | `string \| undefined` | Query, Optional | - |
| `limit` | `number \| undefined` | Query, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`authorizations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const eventContext = 'event_context0';

try {
  const response = await appsEventAuthorizationsApi.appsEventAuthorizationsList(
    token,
    eventContext
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

