# Usergroups

```ts
const usergroupsApi = new UsergroupsApi(client);
```

## Class Name

`UsergroupsApi`

## Methods

* [Usergroups Create](../../doc/controllers/usergroups.md#usergroups-create)
* [Usergroups Disable](../../doc/controllers/usergroups.md#usergroups-disable)
* [Usergroups Enable](../../doc/controllers/usergroups.md#usergroups-enable)
* [Usergroups List](../../doc/controllers/usergroups.md#usergroups-list)
* [Usergroups Update](../../doc/controllers/usergroups.md#usergroups-update)


# Usergroups Create

Create a User Group

API method documentation: [https://api.slack.com/methods/usergroups.create](https://api.slack.com/methods/usergroups.create)

```ts
async usergroupsCreate(
  token: string,
  name: string,
  channels?: string,
  description?: string,
  handle?: string,
  includeCount?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsergroupsCreateSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `name` | `string` | Form, Required | A name for the User Group. Must be unique among User Groups. |
| `channels` | `string \| undefined` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `description` | `string \| undefined` | Form, Optional | A short description of the User Group. |
| `handle` | `string \| undefined` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `includeCount` | `boolean \| undefined` | Form, Optional | Include the number of users in each User Group. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsergroupsCreateSchema`](../../doc/models/usergroups-create-schema.md).

## Example Usage

```ts
const token = 'token6';

const name = 'name0';

try {
  const response = await usergroupsApi.usergroupsCreate(
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
    if (error instanceof UsergroupsCreateErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsCreateErrorSchemaError`](../../doc/models/usergroups-create-error-schema-error.md) |


# Usergroups Disable

Disable an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.disable](https://api.slack.com/methods/usergroups.disable)

```ts
async usergroupsDisable(
  token: string,
  usergroup: string,
  includeCount?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsergroupsDisableSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to disable. |
| `includeCount` | `boolean \| undefined` | Form, Optional | Include the number of users in the User Group. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsergroupsDisableSchema`](../../doc/models/usergroups-disable-schema.md).

## Example Usage

```ts
const token = 'token6';

const usergroup = 'usergroup2';

try {
  const response = await usergroupsApi.usergroupsDisable(
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
    if (error instanceof UsergroupsDisableErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsDisableErrorSchemaError`](../../doc/models/usergroups-disable-error-schema-error.md) |


# Usergroups Enable

Enable a User Group

API method documentation: [https://api.slack.com/methods/usergroups.enable](https://api.slack.com/methods/usergroups.enable)

```ts
async usergroupsEnable(
  token: string,
  usergroup: string,
  includeCount?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsergroupsEnableSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to enable. |
| `includeCount` | `boolean \| undefined` | Form, Optional | Include the number of users in the User Group. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsergroupsEnableSchema`](../../doc/models/usergroups-enable-schema.md).

## Example Usage

```ts
const token = 'token6';

const usergroup = 'usergroup2';

try {
  const response = await usergroupsApi.usergroupsEnable(
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
    if (error instanceof UsergroupsEnableErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsEnableErrorSchemaError`](../../doc/models/usergroups-enable-error-schema-error.md) |


# Usergroups List

List all User Groups for a team

API method documentation: [https://api.slack.com/methods/usergroups.list](https://api.slack.com/methods/usergroups.list)

```ts
async usergroupsList(
  token: string,
  includeUsers?: boolean,
  includeCount?: boolean,
  includeDisabled?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsergroupsListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `usergroups:read` |
| `includeUsers` | `boolean \| undefined` | Query, Optional | Include the list of users for each User Group. |
| `includeCount` | `boolean \| undefined` | Query, Optional | Include the number of users in each User Group. |
| `includeDisabled` | `boolean \| undefined` | Query, Optional | Include disabled User Groups. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsergroupsListSchema`](../../doc/models/usergroups-list-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await usergroupsApi.usergroupsList(token);

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
    if (error instanceof UsergroupsListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsListErrorSchemaError`](../../doc/models/usergroups-list-error-schema-error.md) |


# Usergroups Update

Update an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.update](https://api.slack.com/methods/usergroups.update)

```ts
async usergroupsUpdate(
  token: string,
  usergroup: string,
  handle?: string,
  description?: string,
  channels?: string,
  includeCount?: boolean,
  name?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<UsergroupsUpdateSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `string` | Form, Required | The encoded ID of the User Group to update. |
| `handle` | `string \| undefined` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `description` | `string \| undefined` | Form, Optional | A short description of the User Group. |
| `channels` | `string \| undefined` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `includeCount` | `boolean \| undefined` | Form, Optional | Include the number of users in the User Group. |
| `name` | `string \| undefined` | Form, Optional | A name for the User Group. Must be unique among User Groups. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`UsergroupsUpdateSchema`](../../doc/models/usergroups-update-schema.md).

## Example Usage

```ts
const token = 'token6';

const usergroup = 'usergroup2';

try {
  const response = await usergroupsApi.usergroupsUpdate(
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
    if (error instanceof UsergroupsUpdateErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsergroupsUpdateErrorSchemaError`](../../doc/models/usergroups-update-error-schema-error.md) |

