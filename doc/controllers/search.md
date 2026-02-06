# Search

```ts
const searchApi = new SearchApi(client);
```

## Class Name

`SearchApi`


# Search Messages

Searches for messages matching a query.

API method documentation: [https://api.slack.com/methods/search.messages](https://api.slack.com/methods/search.messages)

```ts
async searchMessages(
  token: string,
  query: string,
  count?: number,
  highlight?: boolean,
  page?: number,
  sort?: string,
  sortDir?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `search:read` |
| `query` | `string` | Query, Required | Search query. |
| `count` | `number \| undefined` | Query, Optional | Pass the number of results you want per "page". Maximum of `100`. |
| `highlight` | `boolean \| undefined` | Query, Optional | Pass a value of `true` to enable query highlight markers (see below). |
| `page` | `number \| undefined` | Query, Optional | - |
| `sort` | `string \| undefined` | Query, Optional | Return matches sorted by either `score` or `timestamp`. |
| `sortDir` | `string \| undefined` | Query, Optional | Change sort direction to ascending (`asc`) or descending (`desc`). |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`search:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const query = 'query0';

try {
  const response = await searchApi.searchMessages(
    token,
    query
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

