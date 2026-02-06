# Auth

```ts
const authApi = new AuthApi(client);
```

## Class Name

`AuthApi`

## Methods

* [Auth Revoke](../../doc/controllers/auth.md#auth-revoke)
* [Auth Test](../../doc/controllers/auth.md#auth-test)


# Auth Revoke

Revokes a token.

API method documentation: [https://api.slack.com/methods/auth.revoke](https://api.slack.com/methods/auth.revoke)

```ts
async authRevoke(
  token: string,
  test?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AuthRevokeSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `test` | `boolean \| undefined` | Query, Optional | Setting this parameter to `1` triggers a _testing mode_ where the specified token will not actually be revoked. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AuthRevokeSchema`](../../doc/models/auth-revoke-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await authApi.authRevoke(token);

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
    if (error instanceof AuthRevokeErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AuthRevokeErrorSchemaError`](../../doc/models/auth-revoke-error-schema-error.md) |


# Auth Test

Checks authentication & identity.

API method documentation: [https://api.slack.com/methods/auth.test](https://api.slack.com/methods/auth.test)

```ts
async authTest(
  token: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AuthTestSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AuthTestSuccessSchema`](../../doc/models/auth-test-success-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await authApi.authTest(token);

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
    if (error instanceof AuthTestErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`AuthTestErrorSchemaError`](../../doc/models/auth-test-error-schema-error.md) |

