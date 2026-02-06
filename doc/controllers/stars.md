# Stars

```ts
const starsApi = new StarsApi(client);
```

## Class Name

`StarsApi`

## Methods

* [Stars Add](../../doc/controllers/stars.md#stars-add)
* [Stars List](../../doc/controllers/stars.md#stars-list)
* [Stars Remove](../../doc/controllers/stars.md#stars-remove)


# Stars Add

Adds a star to an item.

API method documentation: [https://api.slack.com/methods/stars.add](https://api.slack.com/methods/stars.add)

```ts
async starsAdd(
  token: string,
  channel?: string,
  file?: string,
  fileComment?: string,
  timestamp?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<StarsAddSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `string \| undefined` | Form, Optional | Channel to add star to, or channel where the message to add star to was posted (used with `timestamp`). |
| `file` | `string \| undefined` | Form, Optional | File to add star to. |
| `fileComment` | `string \| undefined` | Form, Optional | File comment to add star to. |
| `timestamp` | `string \| undefined` | Form, Optional | Timestamp of the message to add star to. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`StarsAddSchema`](../../doc/models/stars-add-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await starsApi.starsAdd(token);

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
    if (error instanceof StarsAddErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsAddErrorSchemaError`](../../doc/models/stars-add-error-schema-error.md) |


# Stars List

Lists stars for a user.

API method documentation: [https://api.slack.com/methods/stars.list](https://api.slack.com/methods/stars.list)

```ts
async starsList(
  token?: string,
  count?: string,
  page?: string,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<StarsListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `stars:read` |
| `count` | `string \| undefined` | Query, Optional | - |
| `page` | `string \| undefined` | Query, Optional | - |
| `cursor` | `string \| undefined` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. See [pagination](/docs/pagination) for more details. |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`stars:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`StarsListSchema`](../../doc/models/stars-list-schema.md).

## Example Usage

```ts
try {
  const response = await starsApi.starsList();

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
    if (error instanceof StarsListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsListErrorSchemaError`](../../doc/models/stars-list-error-schema-error.md) |


# Stars Remove

Removes a star from an item.

API method documentation: [https://api.slack.com/methods/stars.remove](https://api.slack.com/methods/stars.remove)

```ts
async starsRemove(
  token: string,
  channel?: string,
  file?: string,
  fileComment?: string,
  timestamp?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<StarsRemoveSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `string \| undefined` | Form, Optional | Channel to remove star from, or channel where the message to remove star from was posted (used with `timestamp`). |
| `file` | `string \| undefined` | Form, Optional | File to remove star from. |
| `fileComment` | `string \| undefined` | Form, Optional | File comment to remove star from. |
| `timestamp` | `string \| undefined` | Form, Optional | Timestamp of the message to remove star from. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`StarsRemoveSchema`](../../doc/models/stars-remove-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await starsApi.starsRemove(token);

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
    if (error instanceof StarsRemoveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`StarsRemoveErrorSchemaError`](../../doc/models/stars-remove-error-schema-error.md) |

