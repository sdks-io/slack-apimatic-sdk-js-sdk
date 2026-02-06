# Oauth V 2

```ts
const oauthV2Api = new OauthV2Api(client);
```

## Class Name

`OauthV2Api`


# Oauth V 2 Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.v2.access](https://api.slack.com/methods/oauth.v2.access)

```ts
async oauthV2Access(
  code: string,
  clientId?: string,
  clientSecret?: string,
  redirectUri?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `string` | Query, Required | The `code` param returned via the OAuth callback. |
| `clientId` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `string \| undefined` | Query, Optional | Issued when you created your application. |
| `redirectUri` | `string \| undefined` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const code = 'code8';

try {
  const response = await oauthV2Api.oauthV2Access(code);

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

