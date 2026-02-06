# Usergroups Users

```ts
const usergroupsUsersApi = new UsergroupsUsersApi(client);
```

## Class Name

`UsergroupsUsersApi`

## Methods

* [Usergroups Users List](../../doc/controllers/usergroups-users.md#usergroups-users-list)
* [Usergroups Users Update](../../doc/controllers/usergroups-users.md#usergroups-users-update)


# Usergroups Users List

List all users in a User Group

API method documentation: [https://api.slack.com/methods/usergroups.users.list](https://api.slack.com/methods/usergroups.users.list)

```ts
async usergroupsUsersList(
  token: string,
  usergroup: string,
  includeDisabled?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsergroupsUsersListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `usergroups:read` |
| `usergroup` | `string` | Query, Required | The encoded ID of the User Group to update. |
| `includeDisabled` | `boolean \| undefined` | Query, Optional | Allow results that involve disabled User Groups. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsergroupsUsersListSchema`](../../doc/models/usergroups-users-list-schema.md).

## Example Usage

```ts
const token = 'token6';

const usergroup = 'usergroup2';

try {
  const response = await usergroupsUsersApi.usergroupsUsersList(
    token,
    usergroup
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
    if (error instanceof UsergroupsUsersListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`UsergroupsUsersListErrorSchemaError`](../../doc/models/usergroups-users-list-error-schema-error.md) |


# Usergroups Users Update

Update the list of users for a User Group

API method documentation: [https://api.slack.com/methods/usergroups.users.update](https://api.slack.com/methods/usergroups.users.update)

```ts
async usergroupsUsersUpdate(
  token: string,
  usergroup: string,
  users: string,
  includeCount?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsergroupsUsersUpdateSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to update. |
| `users` | `string` | Form, Required | A comma separated string of encoded user IDs that represent the entire list of users for the User Group. |
| `includeCount` | `boolean \| undefined` | Form, Optional | Include the number of users in the User Group. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsergroupsUsersUpdateSchema`](../../doc/models/usergroups-users-update-schema.md).

## Example Usage

```ts
const token = 'token6';

const usergroup = 'usergroup2';

const users = 'users6';

try {
  const response = await usergroupsUsersApi.usergroupsUsersUpdate(
    token,
    usergroup,
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
    if (error instanceof UsergroupsUsersUpdateErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsUsersUpdateErrorSchemaError`](../../doc/models/usergroups-users-update-error-schema-error.md) |

