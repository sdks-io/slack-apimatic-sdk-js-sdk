# Admin Teams Settings

```ts
const adminTeamsSettingsApi = new AdminTeamsSettingsApi(client);
```

## Class Name

`AdminTeamsSettingsApi`

## Methods

* [Admin Teams Settings Info](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-info)
* [Admin Teams Settings Set Default Channels](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-default-channels)
* [Admin Teams Settings Set Description](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-description)
* [Admin Teams Settings Set Discoverability](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-discoverability)
* [Admin Teams Settings Set Icon](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-icon)
* [Admin Teams Settings Set Name](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-name)


# Admin Teams Settings Info

Fetch information about settings in a workspace

API method documentation: [https://api.slack.com/methods/admin.teams.settings.info](https://api.slack.com/methods/admin.teams.settings.info)

```ts
async adminTeamsSettingsInfo(
  token: string,
  teamId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:read` |
| `teamId` | `string` | Query, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamId = 'team_id6';

try {
  const response = await adminTeamsSettingsApi.adminTeamsSettingsInfo(
    token,
    teamId
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


# Admin Teams Settings Set Default Channels

Set the default channels of a workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDefaultChannels](https://api.slack.com/methods/admin.teams.settings.setDefaultChannels)

```ts
async adminTeamsSettingsSetDefaultChannels(
  token: string,
  teamId: string,
  channelIds: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | ID for the workspace to set the default channel for. |
| `channelIds` | `string` | Form, Required | An array of channel IDs. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamId = 'team_id6';

const channelIds = 'channel_ids8';

try {
  const response = await adminTeamsSettingsApi.adminTeamsSettingsSetDefaultChannels(
    token,
    teamId,
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
| Default | Typical error response | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |


# Admin Teams Settings Set Description

Set the description of a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDescription](https://api.slack.com/methods/admin.teams.settings.setDescription)

```ts
async adminTeamsSettingsSetDescription(
  token: string,
  teamId: string,
  description: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | ID for the workspace to set the description for. |
| `description` | `string` | Form, Required | The new description for the workspace. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamId = 'team_id6';

const description = 'description0';

try {
  const response = await adminTeamsSettingsApi.adminTeamsSettingsSetDescription(
    token,
    teamId,
    description
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


# Admin Teams Settings Set Discoverability

An API method that allows admins to set the discoverability of a given workspace

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDiscoverability](https://api.slack.com/methods/admin.teams.settings.setDiscoverability)

```ts
async adminTeamsSettingsSetDiscoverability(
  token: string,
  teamId: string,
  discoverability: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | The ID of the workspace to set discoverability on. |
| `discoverability` | `string` | Form, Required | This workspace's discovery setting. It must be set to one of `open`, `invite_only`, `closed`, or `unlisted`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamId = 'team_id6';

const discoverability = 'discoverability0';

try {
  const response = await adminTeamsSettingsApi.adminTeamsSettingsSetDiscoverability(
    token,
    teamId,
    discoverability
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


# Admin Teams Settings Set Icon

Sets the icon of a workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setIcon](https://api.slack.com/methods/admin.teams.settings.setIcon)

```ts
async adminTeamsSettingsSetIcon(
  token: string,
  imageUrl: string,
  teamId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `imageUrl` | `string` | Form, Required | Image URL for the icon |
| `teamId` | `string` | Form, Required | ID for the workspace to set the icon for. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const imageUrl = 'image_url6';

const teamId = 'team_id6';

try {
  const response = await adminTeamsSettingsApi.adminTeamsSettingsSetIcon(
    token,
    imageUrl,
    teamId
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


# Admin Teams Settings Set Name

Set the name of a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setName](https://api.slack.com/methods/admin.teams.settings.setName)

```ts
async adminTeamsSettingsSetName(
  token: string,
  teamId: string,
  name: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `string` | Form, Required | ID for the workspace to set the name for. |
| `name` | `string` | Form, Required | The new name of the workspace. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamId = 'team_id6';

const name = 'name0';

try {
  const response = await adminTeamsSettingsApi.adminTeamsSettingsSetName(
    token,
    teamId,
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

