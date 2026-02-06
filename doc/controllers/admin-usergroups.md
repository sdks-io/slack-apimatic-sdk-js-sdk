# Admin Usergroups

```ts
const adminUsergroupsApi = new AdminUsergroupsApi(client);
```

## Class Name

`AdminUsergroupsApi`

## Methods

* [Admin Usergroups Add Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-add-channels)
* [Admin Usergroups Add Teams](../../doc/controllers/admin-usergroups.md#admin-usergroups-add-teams)
* [Admin Usergroups List Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-list-channels)
* [Admin Usergroups Remove Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-remove-channels)


# Admin Usergroups Add Channels

Add one or more default channels to an IDP group.

API method documentation: [https://api.slack.com/methods/admin.usergroups.addChannels](https://api.slack.com/methods/admin.usergroups.addChannels)

```ts
async adminUsergroupsAddChannels(
  token: string,
  usergroupId: string,
  channelIds: string,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.usergroups:write` |
| `usergroupId` | `string` | Form, Required | ID of the IDP group to add default channels for. |
| `channelIds` | `string` | Form, Required | Comma separated string of channel IDs. |
| `teamId` | `string \| undefined` | Form, Optional | The workspace to add default channels in. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const usergroupId = 'usergroup_id0';

const channelIds = 'channel_ids8';

try {
  const response = await adminUsergroupsApi.adminUsergroupsAddChannels(
    token,
    usergroupId,
    channelIds
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |


# Admin Usergroups Add Teams

Associate one or more default workspaces with an organization-wide IDP group.

API method documentation: [https://api.slack.com/methods/admin.usergroups.addTeams](https://api.slack.com/methods/admin.usergroups.addTeams)

```ts
async adminUsergroupsAddTeams(
  token: string,
  usergroupId: string,
  teamIds: string,
  autoProvision?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `usergroupId` | `string` | Form, Required | An encoded usergroup (IDP Group) ID. |
| `teamIds` | `string` | Form, Required | A comma separated list of encoded team (workspace) IDs. Each workspace *MUST* belong to the organization associated with the token. |
| `autoProvision` | `boolean \| undefined` | Form, Optional | When `true`, this method automatically creates new workspace accounts for the IDP group members. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const usergroupId = 'usergroup_id0';

const teamIds = 'team_ids2';

try {
  const response = await adminUsergroupsApi.adminUsergroupsAddTeams(
    token,
    usergroupId,
    teamIds
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


# Admin Usergroups List Channels

List the channels linked to an org-level IDP group (user group).

API method documentation: [https://api.slack.com/methods/admin.usergroups.listChannels](https://api.slack.com/methods/admin.usergroups.listChannels)

```ts
async adminUsergroupsListChannels(
  token: string,
  usergroupId: string,
  teamId?: string,
  includeNumMembers?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.usergroups:read` |
| `usergroupId` | `string` | Query, Required | ID of the IDP group to list default channels for. |
| `teamId` | `string \| undefined` | Query, Optional | ID of the the workspace. |
| `includeNumMembers` | `boolean \| undefined` | Query, Optional | Flag to include or exclude the count of members per channel. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const usergroupId = 'usergroup_id0';

try {
  const response = await adminUsergroupsApi.adminUsergroupsListChannels(
    token,
    usergroupId
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |


# Admin Usergroups Remove Channels

Remove one or more default channels from an org-level IDP group (user group).

API method documentation: [https://api.slack.com/methods/admin.usergroups.removeChannels](https://api.slack.com/methods/admin.usergroups.removeChannels)

```ts
async adminUsergroupsRemoveChannels(
  token: string,
  usergroupId: string,
  channelIds: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.usergroups:write` |
| `usergroupId` | `string` | Form, Required | ID of the IDP Group |
| `channelIds` | `string` | Form, Required | Comma-separated string of channel IDs |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const usergroupId = 'usergroup_id0';

const channelIds = 'channel_ids8';

try {
  const response = await adminUsergroupsApi.adminUsergroupsRemoveChannels(
    token,
    usergroupId,
    channelIds
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |

