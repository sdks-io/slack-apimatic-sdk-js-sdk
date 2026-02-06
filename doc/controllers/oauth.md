# Oauth

```ts
const oauthApi = new OauthApi(client);
```

## Class Name

`OauthApi`

## Methods

* [Oauth Access](../../doc/controllers/oauth.md#oauth-access)
* [Oauth Token](../../doc/controllers/oauth.md#oauth-token)


# Oauth Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.access](https://api.slack.com/methods/oauth.access)

```ts
async oauthAccess(
  clientId?: string,
  clientSecret?: string,
  code?: string,
  redirectUri?: string,
  singleChannel?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `code` | `string \| undefined` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirectUri` | `string \| undefined` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `singleChannel` | `boolean \| undefined` | Query, Optional | Request the user to add your app only to a single channel. Only valid with a [legacy workspace app](https://api.slack.com/legacy-workspace-apps). |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await oauthApi.oauthAccess();

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


# Oauth Token

Exchanges a temporary OAuth verifier code for a workspace token.

API method documentation: [https://api.slack.com/methods/oauth.token](https://api.slack.com/methods/oauth.token)

```ts
async oauthToken(
  clientId?: string,
  clientSecret?: string,
  code?: string,
  redirectUri?: string,
  singleChannel?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `code` | `string \| undefined` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirectUri` | `string \| undefined` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `singleChannel` | `boolean \| undefined` | Query, Optional | Request the user to add your app only to a single channel. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await oauthApi.oauthToken();

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

