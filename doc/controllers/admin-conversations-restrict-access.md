# Admin Conversations Restrict Access

```ts
const adminConversationsRestrictAccessApi = new AdminConversationsRestrictAccessApi(client);
```

## Class Name

`AdminConversationsRestrictAccessApi`

## Methods

* [Admin Conversations Restrict Access Add Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-add-group)
* [Admin Conversations Restrict Access List Groups](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-list-groups)
* [Admin Conversations Restrict Access Remove Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-remove-group)


# Admin Conversations Restrict Access Add Group

Add an allowlist of IDP groups for accessing a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup)

```ts
async adminConversationsRestrictAccessAddGroup(
  token: string,
  groupId: string,
  channelId: string,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `groupId` | `string` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to be an allowlist for the private channel. |
| `channelId` | `string` | Form, Required | The channel to link this group to. |
| `teamId` | `string \| undefined` | Form, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const groupId = 'group_id0';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsRestrictAccessApi.adminConversationsRestrictAccessAddGroup(
    token,
    groupId,
    channelId
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


# Admin Conversations Restrict Access List Groups

List all IDP Groups linked to a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups](https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups)

```ts
async adminConversationsRestrictAccessListGroups(
  token: string,
  channelId: string,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `string` | Query, Required | - |
| `teamId` | `string \| undefined` | Query, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsRestrictAccessApi.adminConversationsRestrictAccessListGroups(
    token,
    channelId
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


# Admin Conversations Restrict Access Remove Group

Remove a linked IDP group linked from a private channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup)

```ts
async adminConversationsRestrictAccessRemoveGroup(
  token: string,
  teamId: string,
  groupId: string,
  channelId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `teamId` | `string` | Form, Required | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |
| `groupId` | `string` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to remove from the private channel. |
| `channelId` | `string` | Form, Required | The channel to remove the linked group from. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamId = 'team_id6';

const groupId = 'group_id0';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsRestrictAccessApi.adminConversationsRestrictAccessRemoveGroup(
    token,
    teamId,
    groupId,
    channelId
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

