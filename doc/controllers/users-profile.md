# Users Profile

```ts
const usersProfileApi = new UsersProfileApi(client);
```

## Class Name

`UsersProfileApi`

## Methods

* [Users Profile Get](../../doc/controllers/users-profile.md#users-profile-get)
* [Users Profile Set](../../doc/controllers/users-profile.md#users-profile-set)


# Users Profile Get

Retrieves a user's profile information.

API method documentation: [https://api.slack.com/methods/users.profile.get](https://api.slack.com/methods/users.profile.get)

```ts
async usersProfileGet(
  token: string,
  includeLabels?: boolean,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersProfileGetSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users.profile:read` |
| `includeLabels` | `boolean \| undefined` | Query, Optional | Include labels for each ID in custom profile fields |
| `user` | `string \| undefined` | Query, Optional | User to retrieve profile info for |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users.profile:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersProfileGetSchema`](../../doc/models/users-profile-get-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usersProfileApi.usersProfileGet(token);

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
    if (error instanceof UsersProfileGetErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersProfileGetErrorSchemaError`](../../doc/models/users-profile-get-error-schema-error.md) |


# Users Profile Set

Set the profile information for a user.

API method documentation: [https://api.slack.com/methods/users.profile.set](https://api.slack.com/methods/users.profile.set)

```ts
async usersProfileSet(
  token: string,
  name?: string,
  profile?: string,
  user?: string,
  value?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsersProfileSetSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `users.profile:write` |
| `name` | `string \| undefined` | Form, Optional | Name of a single key to set. Usable only if `profile` is not passed. |
| `profile` | `string \| undefined` | Form, Optional | Collection of key:value pairs presented as a URL-encoded JSON hash. At most 50 fields may be set. Each field name is limited to 255 characters. |
| `user` | `string \| undefined` | Form, Optional | ID of user to change. This argument may only be specified by team admins on paid teams. |
| `value` | `string \| undefined` | Form, Optional | Value to set a single key to. Usable only if `profile` is not passed. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsersProfileSetSchema`](../../doc/models/users-profile-set-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usersProfileApi.usersProfileSet(token);

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
    if (error instanceof UsersProfileSetErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersProfileSetErrorSchemaError`](../../doc/models/users-profile-set-error-schema-error.md) |

