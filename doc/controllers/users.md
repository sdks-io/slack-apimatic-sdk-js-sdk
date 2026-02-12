# Users

```ts
const usersApi = new UsersApi(client);
```

## Class Name

`UsersApi`

## Methods

* [Users Conversations](../../doc/controllers/users.md#users-conversations)
* [Users Delete Photo](../../doc/controllers/users.md#users-delete-photo)
* [Users Get Presence](../../doc/controllers/users.md#users-get-presence)
* [Users Identity](../../doc/controllers/users.md#users-identity)
* [Users Info](../../doc/controllers/users.md#users-info)
* [Users List](../../doc/controllers/users.md#users-list)
* [Users Lookup by Email](../../doc/controllers/users.md#users-lookup-by-email)
* [Users Set Active](../../doc/controllers/users.md#users-set-active)
* [Users Set Photo](../../doc/controllers/users.md#users-set-photo)
* [Users Set Presence](../../doc/controllers/users.md#users-set-presence)


# Users Conversations

List conversations the calling user may access.

API method documentation: [https://api.slack.com/methods/users.conversations](https://api.slack.com/methods/users.conversations)

```ts
async usersConversations(
  token?: string,
  user?: string,
  types?: string,
  excludeArchived?: boolean,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersConversationsSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `user` | `string \| undefined` | Query, Optional | Browse conversations by a specific user ID's membership. Non-public channels are restricted to those where the calling user shares membership. |
| `types` | `string \| undefined` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `excludeArchived` | `boolean \| undefined` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersConversationsSuccessSchema`](../../doc/models/users-conversations-success-schema.md).

## Example Usage

```ts
try {
  const response = await usersApi.usersConversations();

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
    if (error instanceof UsersConversationsErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersConversationsErrorSchemaError`](../../doc/models/users-conversations-error-schema-error.md) |


# Users Delete Photo

Delete the user profile photo

API method documentation: [https://api.slack.com/methods/users.deletePhoto](https://api.slack.com/methods/users.deletePhoto)

```ts
async usersDeletePhoto(
  token: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersDeletePhotoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `users.profile:write` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersDeletePhotoSchema`](../../doc/models/users-delete-photo-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usersApi.usersDeletePhoto(token);

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
    if (error instanceof UsersDeletePhotoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersDeletePhotoErrorSchemaError`](../../doc/models/users-delete-photo-error-schema-error.md) |


# Users Get Presence

Gets user presence information.

API method documentation: [https://api.slack.com/methods/users.getPresence](https://api.slack.com/methods/users.getPresence)

```ts
async usersGetPresence(
  token: string,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ApiMethodUsersGetPresence>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read` |
| `user` | `string \| undefined` | Query, Optional | User to get presence info on. Defaults to the authed user. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ApiMethodUsersGetPresence`](../../doc/models/api-method-users-get-presence.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usersApi.usersGetPresence(token);

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
    if (error instanceof UsersCountsErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersCountsErrorSchemaError`](../../doc/models/users-counts-error-schema-error.md) |


# Users Identity

Get a user's identity.

API method documentation: [https://api.slack.com/methods/users.identity](https://api.slack.com/methods/users.identity)

```ts
async usersIdentity(
  token?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `identity.basic` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`identity.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
try {
  const response = await usersApi.usersIdentity();

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
    if (error instanceof UsersIdentityErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Example Response

```
{
  "ok": true,
  "team": {
    "id": "T0G9PQBBK"
  },
  "user": {
    "id": "U0G9QF9C6",
    "name": "Sonny Whether"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersIdentityErrorSchemaError`](../../doc/models/users-identity-error-schema-error.md) |


# Users Info

Gets information about a user.

API method documentation: [https://api.slack.com/methods/users.info](https://api.slack.com/methods/users.info)

```ts
async usersInfo(
  token: string,
  includeLocale?: boolean,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersInfoSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read` |
| `includeLocale` | `boolean \| undefined` | Query, Optional | Set this to `true` to receive the locale for this user. Defaults to `false` |
| `user` | `string \| undefined` | Query, Optional | User to get info on |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersInfoSuccessSchema`](../../doc/models/users-info-success-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usersApi.usersInfo(token);

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
    if (error instanceof UsersInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersInfoErrorSchemaError`](../../doc/models/users-info-error-schema-error.md) |


# Users List

Lists all users in a Slack team.

API method documentation: [https://api.slack.com/methods/users.list](https://api.slack.com/methods/users.list)

```ts
async usersList(
  token?: string,
  limit?: number,
  cursor?: string,
  includeLocale?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `users:read` |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. Providing no `limit` value will result in Slack attempting to deliver you the entire result set. If the collection is too large you may experience `limit_required` or HTTP 500 errors. |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |
| `includeLocale` | `boolean \| undefined` | Query, Optional | Set this to `true` to receive the locale for users. Defaults to `false` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersListSchema`](../../doc/models/users-list-schema.md).

## Example Usage

```ts
try {
  const response = await usersApi.usersList();

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
    if (error instanceof UsersListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersListErrorSchemaError`](../../doc/models/users-list-error-schema-error.md) |


# Users Lookup by Email

Find a user with an email address.

API method documentation: [https://api.slack.com/methods/users.lookupByEmail](https://api.slack.com/methods/users.lookupByEmail)

```ts
async usersLookupByEmail(
  token: string,
  email: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersLookupByEmailSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users:read.email` |
| `email` | `string` | Query, Required | An email address belonging to a user in the workspace |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users:read.email`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersLookupByEmailSuccessSchema`](../../doc/models/users-lookup-by-email-success-schema.md).

## Example Usage

```ts
const token = 'token6';

const email = 'email6';

try {
  const response = await usersApi.usersLookupByEmail(
    token,
    email
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
    if (error instanceof UsersLookupByEmailErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersLookupByEmailErrorSchemaError`](../../doc/models/users-lookup-by-email-error-schema-error.md) |


# Users Set Active

Marked a user as active. Deprecated and non-functional.

API method documentation: [https://api.slack.com/methods/users.setActive](https://api.slack.com/methods/users.setActive)

```ts
async usersSetActive(
  token: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersSetActiveSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `users:write` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersSetActiveSchema`](../../doc/models/users-set-active-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usersApi.usersSetActive(token);

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
    if (error instanceof UsersSetActiveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetActiveErrorSchemaError`](../../doc/models/users-set-active-error-schema-error.md) |


# Users Set Photo

Set the user profile photo

API method documentation: [https://api.slack.com/methods/users.setPhoto](https://api.slack.com/methods/users.setPhoto)

```ts
async usersSetPhoto(
  token: string,
  cropW?: string,
  cropX?: string,
  cropY?: string,
  image?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersSetPhotoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `users.profile:write` |
| `cropW` | `string \| undefined` | Form, Optional | Width/height of crop box (always square) |
| `cropX` | `string \| undefined` | Form, Optional | X coordinate of top-left corner of crop box |
| `cropY` | `string \| undefined` | Form, Optional | Y coordinate of top-left corner of crop box |
| `image` | `string \| undefined` | Form, Optional | File contents via `multipart/form-data`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersSetPhotoSchema`](../../doc/models/users-set-photo-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usersApi.usersSetPhoto(token);

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
    if (error instanceof UsersSetPhotoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetPhotoErrorSchemaError`](../../doc/models/users-set-photo-error-schema-error.md) |


# Users Set Presence

Manually sets user presence.

API method documentation: [https://api.slack.com/methods/users.setPresence](https://api.slack.com/methods/users.setPresence)

```ts
async usersSetPresence(
  token: string,
  presence: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersSetPresenceSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `users:write` |
| `presence` | `string` | Form, Required | Either `auto` or `away` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersSetPresenceSchema`](../../doc/models/users-set-presence-schema.md).

## Example Usage

```ts
const token = 'token6';

const presence = 'presence4';

try {
  const response = await usersApi.usersSetPresence(
    token,
    presence
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
    if (error instanceof UsersSetPresenceErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersSetPresenceErrorSchemaError`](../../doc/models/users-set-presence-error-schema-error.md) |

