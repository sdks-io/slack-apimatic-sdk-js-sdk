# Reminders

```ts
const remindersApi = new RemindersApi(client);
```

## Class Name

`RemindersApi`

## Methods

* [Reminders Add](../../doc/controllers/reminders.md#reminders-add)
* [Reminders Complete](../../doc/controllers/reminders.md#reminders-complete)
* [Reminders Delete](../../doc/controllers/reminders.md#reminders-delete)
* [Reminders Info](../../doc/controllers/reminders.md#reminders-info)
* [Reminders List](../../doc/controllers/reminders.md#reminders-list)


# Reminders Add

Creates a reminder.

API method documentation: [https://api.slack.com/methods/reminders.add](https://api.slack.com/methods/reminders.add)

```ts
async remindersAdd(
  token: string,
  text: string,
  time: string,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RemindersAddSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `reminders:write` |
| `text` | `string` | Form, Required | The content of the reminder |
| `time` | `string` | Form, Required | When this reminder should happen: the Unix timestamp (up to five years from now), the number of seconds until the reminder (if within 24 hours), or a natural language description (Ex. "in 15 minutes," or "every Thursday") |
| `user` | `string \| undefined` | Form, Optional | The user who will receive the reminder. If no user is specified, the reminder will go to user who created it. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RemindersAddSchema`](../../doc/models/reminders-add-schema.md).

## Example Usage

```ts
const token = 'token6';

const text = 'text0';

const time = 'time0';

try {
  const response = await remindersApi.remindersAdd(
    token,
    text,
    time
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
    if (error instanceof RemindersAddErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersAddErrorSchemaError`](../../doc/models/reminders-add-error-schema-error.md) |


# Reminders Complete

Marks a reminder as complete.

API method documentation: [https://api.slack.com/methods/reminders.complete](https://api.slack.com/methods/reminders.complete)

```ts
async remindersComplete(
  token?: string,
  reminder?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RemindersCompleteSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `string \| undefined` | Form, Optional | The ID of the reminder to be marked as complete |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RemindersCompleteSchema`](../../doc/models/reminders-complete-schema.md).

## Example Usage

```ts
try {
  const response = await remindersApi.remindersComplete();

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
    if (error instanceof RemindersCompleteErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersCompleteErrorSchemaError`](../../doc/models/reminders-complete-error-schema-error.md) |


# Reminders Delete

Deletes a reminder.

API method documentation: [https://api.slack.com/methods/reminders.delete](https://api.slack.com/methods/reminders.delete)

```ts
async remindersDelete(
  token?: string,
  reminder?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RemindersDeleteSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `string \| undefined` | Form, Optional | The ID of the reminder |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RemindersDeleteSchema`](../../doc/models/reminders-delete-schema.md).

## Example Usage

```ts
try {
  const response = await remindersApi.remindersDelete();

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
    if (error instanceof RemindersDeleteErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersDeleteErrorSchemaError`](../../doc/models/reminders-delete-error-schema-error.md) |


# Reminders Info

Gets information about a reminder.

API method documentation: [https://api.slack.com/methods/reminders.info](https://api.slack.com/methods/reminders.info)

```ts
async remindersInfo(
  token?: string,
  reminder?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RemindersInfoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `reminders:read` |
| `reminder` | `string \| undefined` | Query, Optional | The ID of the reminder |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RemindersInfoSchema`](../../doc/models/reminders-info-schema.md).

## Example Usage

```ts
try {
  const response = await remindersApi.remindersInfo();

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
    if (error instanceof RemindersInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersInfoErrorSchemaError`](../../doc/models/reminders-info-error-schema-error.md) |


# Reminders List

Lists all reminders created by or for a given user.

API method documentation: [https://api.slack.com/methods/reminders.list](https://api.slack.com/methods/reminders.list)

```ts
async remindersList(
  token?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RemindersListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `reminders:read` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RemindersListSchema`](../../doc/models/reminders-list-schema.md).

## Example Usage

```ts
try {
  const response = await remindersApi.remindersList();

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
    if (error instanceof RemindersListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RemindersListErrorSchemaError`](../../doc/models/reminders-list-error-schema-error.md) |

