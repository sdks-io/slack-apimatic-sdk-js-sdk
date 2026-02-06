# Bots

```ts
const botsApi = new BotsApi(client);
```

## Class Name

`BotsApi`


# Bots Info

Gets information about a bot user.

API method documentation: [https://api.slack.com/methods/bots.info](https://api.slack.com/methods/bots.info)

```ts
async botsInfo(
  token: string,
  bot?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<BotsInfoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read` |
| `bot` | `string \| undefined` | Query, Optional | Bot user to get info on |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`BotsInfoSchema`](../../doc/models/bots-info-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await botsApi.botsInfo(token);

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
    if (error instanceof BotsInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | When no bot can be found, it returns an error. | [`BotsInfoErrorSchemaError`](../../doc/models/bots-info-error-schema-error.md) |

