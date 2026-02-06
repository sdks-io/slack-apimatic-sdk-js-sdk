# Calls

```ts
const callsApi = new CallsApi(client);
```

## Class Name

`CallsApi`

## Methods

* [Calls Add](../../doc/controllers/calls.md#calls-add)
* [Calls End](../../doc/controllers/calls.md#calls-end)
* [Calls Info](../../doc/controllers/calls.md#calls-info)
* [Calls Update](../../doc/controllers/calls.md#calls-update)


# Calls Add

Registers a new Call.

API method documentation: [https://api.slack.com/methods/calls.add](https://api.slack.com/methods/calls.add)

```ts
async callsAdd(
  token: string,
  externalUniqueId: string,
  joinUrl: string,
  externalDisplayId?: string,
  desktopAppJoinUrl?: string,
  dateStart?: number,
  title?: string,
  createdBy?: string,
  users?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `externalUniqueId` | `string` | Form, Required | An ID supplied by the 3rd-party Call provider. It must be unique across all Calls from that service. |
| `joinUrl` | `string` | Form, Required | The URL required for a client to join the Call. |
| `externalDisplayId` | `string \| undefined` | Form, Optional | An optional, human-readable ID supplied by the 3rd-party Call provider. If supplied, this ID will be displayed in the Call object. |
| `desktopAppJoinUrl` | `string \| undefined` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |
| `dateStart` | `number \| undefined` | Form, Optional | Call start time in UTC UNIX timestamp format |
| `title` | `string \| undefined` | Form, Optional | The name of the Call. |
| `createdBy` | `string \| undefined` | Form, Optional | The valid Slack user ID of the user who created this Call. When this method is called with a user token, the `created_by` field is optional and defaults to the authed user of the token. Otherwise, the field is required. |
| `users` | `string \| undefined` | Form, Optional | The list of users to register as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const externalUniqueId = 'external_unique_id0';

const joinUrl = 'join_url6';

try {
  const response = await callsApi.callsAdd(
    token,
    externalUniqueId,
    joinUrl
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


# Calls End

Ends a Call.

API method documentation: [https://api.slack.com/methods/calls.end](https://api.slack.com/methods/calls.end)

```ts
async callsEnd(
  token: string,
  id: string,
  duration?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned when registering the call using the [`calls.add`](/methods/calls.add) method. |
| `duration` | `number \| undefined` | Form, Optional | Call duration in seconds |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const id = 'id0';

try {
  const response = await callsApi.callsEnd(
    token,
    id
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


# Calls Info

Returns information about a Call.

API method documentation: [https://api.slack.com/methods/calls.info](https://api.slack.com/methods/calls.info)

```ts
async callsInfo(
  token: string,
  id: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:read` |
| `id` | `string` | Query, Required | `id` of the Call returned by the [`calls.add`](/methods/calls.add) method. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`calls:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const id = 'id0';

try {
  const response = await callsApi.callsInfo(
    token,
    id
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


# Calls Update

Updates information about a Call.

API method documentation: [https://api.slack.com/methods/calls.update](https://api.slack.com/methods/calls.update)

```ts
async callsUpdate(
  token: string,
  id: string,
  title?: string,
  joinUrl?: string,
  desktopAppJoinUrl?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `title` | `string \| undefined` | Form, Optional | The name of the Call. |
| `joinUrl` | `string \| undefined` | Form, Optional | The URL required for a client to join the Call. |
| `desktopAppJoinUrl` | `string \| undefined` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const id = 'id0';

try {
  const response = await callsApi.callsUpdate(
    token,
    id
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

