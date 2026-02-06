# Calls Participants

```ts
const callsParticipantsApi = new CallsParticipantsApi(client);
```

## Class Name

`CallsParticipantsApi`

## Methods

* [Calls Participants Add](../../doc/controllers/calls-participants.md#calls-participants-add)
* [Calls Participants Remove](../../doc/controllers/calls-participants.md#calls-participants-remove)


# Calls Participants Add

Registers new participants added to a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.add](https://api.slack.com/methods/calls.participants.add)

```ts
async callsParticipantsAdd(
  token: string,
  id: string,
  users: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `string` | Form, Required | The list of users to add as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |
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

const users = 'users6';

try {
  const response = await callsParticipantsApi.callsParticipantsAdd(
    token,
    id,
    users
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


# Calls Participants Remove

Registers participants removed from a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.remove](https://api.slack.com/methods/calls.participants.remove)

```ts
async callsParticipantsRemove(
  token: string,
  id: string,
  users: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `string` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `string` | Form, Required | The list of users to remove as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |
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

const users = 'users6';

try {
  const response = await callsParticipantsApi.callsParticipantsRemove(
    token,
    id,
    users
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

