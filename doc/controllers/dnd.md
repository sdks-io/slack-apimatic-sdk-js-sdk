# Dnd

```ts
const dndApi = new DndApi(client);
```

## Class Name

`DndApi`

## Methods

* [Dnd End Dnd](../../doc/controllers/dnd.md#dnd-end-dnd)
* [Dnd End Snooze](../../doc/controllers/dnd.md#dnd-end-snooze)
* [Dnd Info](../../doc/controllers/dnd.md#dnd-info)
* [Dnd Set Snooze](../../doc/controllers/dnd.md#dnd-set-snooze)
* [Dnd Team Info](../../doc/controllers/dnd.md#dnd-team-info)


# Dnd End Dnd

Ends the current user's Do Not Disturb session immediately.

API method documentation: [https://api.slack.com/methods/dnd.endDnd](https://api.slack.com/methods/dnd.endDnd)

```ts
async dndEndDnd(
  token: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DndEndDndSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `dnd:write` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DndEndDndSchema`](../../doc/models/dnd-end-dnd-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await dndApi.dndEndDnd(token);

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
    if (error instanceof DndEndDndErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndEndDndErrorSchemaError`](../../doc/models/dnd-end-dnd-error-schema-error.md) |


# Dnd End Snooze

Ends the current user's snooze mode immediately.

API method documentation: [https://api.slack.com/methods/dnd.endSnooze](https://api.slack.com/methods/dnd.endSnooze)

```ts
async dndEndSnooze(
  token: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DndEndSnoozeSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `dnd:write` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DndEndSnoozeSchema`](../../doc/models/dnd-end-snooze-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await dndApi.dndEndSnooze(token);

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
    if (error instanceof DndEndSnoozeErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndEndSnoozeErrorSchemaError`](../../doc/models/dnd-end-snooze-error-schema-error.md) |


# Dnd Info

Retrieves a user's current Do Not Disturb status.

API method documentation: [https://api.slack.com/methods/dnd.info](https://api.slack.com/methods/dnd.info)

```ts
async dndInfo(
  token?: string,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DndInfoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `dnd:read` |
| `user` | `string \| undefined` | Query, Optional | User to fetch status for (defaults to current user) |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`dnd:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DndInfoSchema`](../../doc/models/dnd-info-schema.md).

## Example Usage

```ts
try {
  const response = await dndApi.dndInfo();

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
    if (error instanceof DndInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndInfoErrorSchemaError`](../../doc/models/dnd-info-error-schema-error.md) |


# Dnd Set Snooze

Turns on Do Not Disturb mode for the current user, or changes its duration.

API method documentation: [https://api.slack.com/methods/dnd.setSnooze](https://api.slack.com/methods/dnd.setSnooze)

```ts
async dndSetSnooze(
  token: string,
  numMinutes: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DndSetSnoozeSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `dnd:write` |
| `numMinutes` | `string` | Form, Required | Number of minutes, from now, to snooze until. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DndSetSnoozeSchema`](../../doc/models/dnd-set-snooze-schema.md).

## Example Usage

```ts
const token = 'token6';

const numMinutes = 'num_minutes0';

try {
  const response = await dndApi.dndSetSnooze(
    token,
    numMinutes
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
    if (error instanceof DndSetSnoozeErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DndSetSnoozeErrorSchemaError`](../../doc/models/dnd-set-snooze-error-schema-error.md) |


# Dnd Team Info

Retrieves the Do Not Disturb status for up to 50 users on a team.

API method documentation: [https://api.slack.com/methods/dnd.teamInfo](https://api.slack.com/methods/dnd.teamInfo)

```ts
async dndTeamInfo(
  token?: string,
  users?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `dnd:read` |
| `users` | `string \| undefined` | Query, Optional | Comma-separated list of users to fetch Do Not Disturb status for |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`dnd:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await dndApi.dndTeamInfo();

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

