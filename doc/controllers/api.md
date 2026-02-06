# Api

```ts
const api = new Api(client);
```

## Class Name

`Api`


# Api Test

Checks API calling code.

API method documentation: [https://api.slack.com/methods/api.test](https://api.slack.com/methods/api.test)

```ts
async apiTest(
  error?: string,
  foo?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ApiTestSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | `string \| undefined` | Query, Optional | Error response to return |
| `foo` | `string \| undefined` | Query, Optional | example property to return |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ApiTestSuccessSchema`](../../doc/models/api-test-success-schema.md).

## Example Usage

```ts
try {
  const response = await api.apiTest();

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
    if (error instanceof ApiTestErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Artificial error response | [`ApiTestErrorSchemaError`](../../doc/models/api-test-error-schema-error.md) |

