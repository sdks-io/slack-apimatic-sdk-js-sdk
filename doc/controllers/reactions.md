# Reactions

```ts
const reactionsApi = new ReactionsApi(client);
```

## Class Name

`ReactionsApi`

## Methods

* [Reactions Add](../../doc/controllers/reactions.md#reactions-add)
* [Reactions Get](../../doc/controllers/reactions.md#reactions-get)
* [Reactions List](../../doc/controllers/reactions.md#reactions-list)
* [Reactions Remove](../../doc/controllers/reactions.md#reactions-remove)


# Reactions Add

Adds a reaction to an item.

API method documentation: [https://api.slack.com/methods/reactions.add](https://api.slack.com/methods/reactions.add)

```ts
async reactionsAdd(
  channel: string,
  name: string,
  timestamp: string,
  token: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ReactionsAddSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `string` | Form, Required | Channel where the message to add reaction to was posted. |
| `name` | `string` | Form, Required | Reaction (emoji) name. |
| `timestamp` | `string` | Form, Required | Timestamp of the message to add reaction to. |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `reactions:write` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ReactionsAddSchema`](../../doc/models/reactions-add-schema.md).

## Example Usage

```ts
const channel = 'channel4';

const name = 'name0';

const timestamp = 'timestamp2';

const token = 'token6';

try {
  const response = await reactionsApi.reactionsAdd(
    channel,
    name,
    timestamp,
    token
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
    if (error instanceof ReactionsAddErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsAddErrorSchemaError`](../../doc/models/reactions-add-error-schema-error.md) |


# Reactions Get

Gets reactions for an item.

API method documentation: [https://api.slack.com/methods/reactions.get](https://api.slack.com/methods/reactions.get)

```ts
async reactionsGet(
  token: string,
  channel?: string,
  file?: string,
  fileComment?: string,
  full?: boolean,
  timestamp?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown | undefined>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `channel` | `string \| undefined` | Query, Optional | Channel where the message to get reactions for was posted. |
| `file` | `string \| undefined` | Query, Optional | File to get reactions for. |
| `fileComment` | `string \| undefined` | Query, Optional | File comment to get reactions for. |
| `full` | `boolean \| undefined` | Query, Optional | If true always return the complete reaction list. |
| `timestamp` | `string \| undefined` | Query, Optional | Timestamp of the message to get reactions for. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const token = 'token6';

try {
  const response = await reactionsApi.reactionsGet(token);

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
    if (error instanceof ReactionsGetErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Example Response

```
{
  "file": {
    "channels": [
      "C2U7V2YA2"
    ],
    "comments_count": 1,
    "created": 1507850315,
    "groups": [],
    "id": "F7H0D7ZA4",
    "ims": [],
    "name": "computer.gif",
    "reactions": [
      {
        "count": 1,
        "name": "stuck_out_tongue_winking_eye",
        "users": [
          "U2U85N1RV"
        ]
      }
    ],
    "timestamp": 1507850315,
    "title": "computer.gif",
    "user": "U2U85N1RV"
  },
  "ok": true,
  "type": "file"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsGetErrorSchemaError`](../../doc/models/reactions-get-error-schema-error.md) |


# Reactions List

Lists reactions made by a user.

API method documentation: [https://api.slack.com/methods/reactions.list](https://api.slack.com/methods/reactions.list)

```ts
async reactionsList(
  token: string,
  user?: string,
  full?: boolean,
  count?: number,
  page?: number,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ReactionsListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `user` | `string \| undefined` | Query, Optional | Show reactions made by this user. Defaults to the authed user. |
| `full` | `boolean \| undefined` | Query, Optional | If true always return the complete reaction list. |
| `count` | `number \| undefined` | Query, Optional | - |
| `page` | `number \| undefined` | Query, Optional | - |
| `cursor` | `string \| undefined` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ReactionsListSchema`](../../doc/models/reactions-list-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await reactionsApi.reactionsList(token);

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
    if (error instanceof ReactionsListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsListErrorSchemaError`](../../doc/models/reactions-list-error-schema-error.md) |


# Reactions Remove

Removes a reaction from an item.

API method documentation: [https://api.slack.com/methods/reactions.remove](https://api.slack.com/methods/reactions.remove)

```ts
async reactionsRemove(
  token: string,
  name: string,
  file?: string,
  fileComment?: string,
  channel?: string,
  timestamp?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ReactionsRemoveSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `reactions:write` |
| `name` | `string` | Form, Required | Reaction (emoji) name. |
| `file` | `string \| undefined` | Form, Optional | File to remove reaction from. |
| `fileComment` | `string \| undefined` | Form, Optional | File comment to remove reaction from. |
| `channel` | `string \| undefined` | Form, Optional | Channel where the message to remove reaction from was posted. |
| `timestamp` | `string \| undefined` | Form, Optional | Timestamp of the message to remove reaction from. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ReactionsRemoveSchema`](../../doc/models/reactions-remove-schema.md).

## Example Usage

```ts
const token = 'token6';

const name = 'name0';

try {
  const response = await reactionsApi.reactionsRemove(
    token,
    name
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
    if (error instanceof ReactionsRemoveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsRemoveErrorSchemaError`](../../doc/models/reactions-remove-error-schema-error.md) |

