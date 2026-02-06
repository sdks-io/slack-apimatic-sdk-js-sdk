# Admin Conversations

```ts
const adminConversationsApi = new AdminConversationsApi(client);
```

## Class Name

`AdminConversationsApi`

## Methods

* [Admin Conversations Archive](../../doc/controllers/admin-conversations.md#admin-conversations-archive)
* [Admin Conversations Convert to Private](../../doc/controllers/admin-conversations.md#admin-conversations-convert-to-private)
* [Admin Conversations Create](../../doc/controllers/admin-conversations.md#admin-conversations-create)
* [Admin Conversations Delete](../../doc/controllers/admin-conversations.md#admin-conversations-delete)
* [Admin Conversations Disconnect Shared](../../doc/controllers/admin-conversations.md#admin-conversations-disconnect-shared)
* [Admin Conversations Get Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-get-conversation-prefs)
* [Admin Conversations Get Teams](../../doc/controllers/admin-conversations.md#admin-conversations-get-teams)
* [Admin Conversations Invite](../../doc/controllers/admin-conversations.md#admin-conversations-invite)
* [Admin Conversations Rename](../../doc/controllers/admin-conversations.md#admin-conversations-rename)
* [Admin Conversations Search](../../doc/controllers/admin-conversations.md#admin-conversations-search)
* [Admin Conversations Set Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-set-conversation-prefs)
* [Admin Conversations Set Teams](../../doc/controllers/admin-conversations.md#admin-conversations-set-teams)
* [Admin Conversations Unarchive](../../doc/controllers/admin-conversations.md#admin-conversations-unarchive)


# Admin Conversations Archive

Archive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.archive](https://api.slack.com/methods/admin.conversations.archive)

```ts
async adminConversationsArchive(
  token: string,
  channelId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsArchiveSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to archive. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsArchiveSchema`](../../doc/models/admin-conversations-archive-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsArchive(
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
    if (error instanceof AdminConversationsArchiveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsArchiveErrorSchemaError`](../../doc/models/admin-conversations-archive-error-schema-error.md) |


# Admin Conversations Convert to Private

Convert a public channel to a private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.convertToPrivate](https://api.slack.com/methods/admin.conversations.convertToPrivate)

```ts
async adminConversationsConvertToPrivate(
  token: string,
  channelId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsConvertToPrivateSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to convert to private. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsConvertToPrivateSchema`](../../doc/models/admin-conversations-convert-to-private-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsConvertToPrivate(
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
    if (error instanceof AdminConversationsConvertToPrivateErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsConvertToPrivateErrorSchemaError`](../../doc/models/admin-conversations-convert-to-private-error-schema-error.md) |


# Admin Conversations Create

Create a public or private channel-based conversation.

API method documentation: [https://api.slack.com/methods/admin.conversations.create](https://api.slack.com/methods/admin.conversations.create)

```ts
async adminConversationsCreate(
  token: string,
  name: string,
  isPrivate: boolean,
  description?: string,
  orgWide?: boolean,
  teamId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsCreateSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `name` | `string` | Form, Required | Name of the public or private channel to create. |
| `isPrivate` | `boolean` | Form, Required | When `true`, creates a private channel instead of a public channel |
| `description` | `string \| undefined` | Form, Optional | Description of the public or private channel to create. |
| `orgWide` | `boolean \| undefined` | Form, Optional | When `true`, the channel will be available org-wide. Note: if the channel is not `org_wide=true`, you must specify a `team_id` for this channel |
| `teamId` | `string \| undefined` | Form, Optional | The workspace to create the channel in. Note: this argument is required unless you set `org_wide=true`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsCreateSchema`](../../doc/models/admin-conversations-create-schema.md).

## Example Usage

```ts
const token = 'token6';

const name = 'name0';

const isPrivate = false;

try {
  const response = await adminConversationsApi.adminConversationsCreate(
    token,
    name,
    isPrivate
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
    if (error instanceof AdminConversationsCreateErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsCreateErrorSchemaError`](../../doc/models/admin-conversations-create-error-schema-error.md) |


# Admin Conversations Delete

Delete a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.delete](https://api.slack.com/methods/admin.conversations.delete)

```ts
async adminConversationsDelete(
  token: string,
  channelId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsDeleteSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to delete. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsDeleteSchema`](../../doc/models/admin-conversations-delete-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsDelete(
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
    if (error instanceof AdminConversationsDeleteErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsDeleteErrorSchemaError`](../../doc/models/admin-conversations-delete-error-schema-error.md) |


# Admin Conversations Disconnect Shared

Disconnect a connected channel from one or more workspaces.

API method documentation: [https://api.slack.com/methods/admin.conversations.disconnectShared](https://api.slack.com/methods/admin.conversations.disconnectShared)

```ts
async adminConversationsDisconnectShared(
  token: string,
  channelId: string,
  leavingTeamIds?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsRenameSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to be disconnected from some workspaces. |
| `leavingTeamIds` | `string \| undefined` | Form, Optional | The team to be removed from the channel. Currently only a single team id can be specified. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsRenameSchema`](../../doc/models/admin-conversations-rename-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsDisconnectShared(
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
    if (error instanceof AdminConversationsDisconnectSharedErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsDisconnectSharedErrorSchemaError`](../../doc/models/admin-conversations-disconnect-shared-error-schema-error.md) |


# Admin Conversations Get Conversation Prefs

Get conversation preferences for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.getConversationPrefs](https://api.slack.com/methods/admin.conversations.getConversationPrefs)

```ts
async adminConversationsGetConversationPrefs(
  token: string,
  channelId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsGetConversationPrefsSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `string` | Query, Required | The channel to get preferences for. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsGetConversationPrefsSchema`](../../doc/models/admin-conversations-get-conversation-prefs-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsGetConversationPrefs(
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
    if (error instanceof AdminConversationsUnarchiveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchemaError`](../../doc/models/admin-conversations-unarchive-error-schema-error.md) |


# Admin Conversations Get Teams

Get all the workspaces a given public or private channel is connected to within this Enterprise org.

API method documentation: [https://api.slack.com/methods/admin.conversations.getTeams](https://api.slack.com/methods/admin.conversations.getTeams)

```ts
async adminConversationsGetTeams(
  token: string,
  channelId: string,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsGetTeamsSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `string` | Query, Required | The channel to determine connected workspaces within the organization for. |
| `cursor` | `string \| undefined` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsGetTeamsSchema`](../../doc/models/admin-conversations-get-teams-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsGetTeams(
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
    if (error instanceof AdminConversationsGetTeamsErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsGetTeamsErrorSchemaError`](../../doc/models/admin-conversations-get-teams-error-schema-error.md) |


# Admin Conversations Invite

Invite a user to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.invite](https://api.slack.com/methods/admin.conversations.invite)

```ts
async adminConversationsInvite(
  token: string,
  userIds: string,
  channelId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsInviteSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `userIds` | `string` | Form, Required | The users to invite. |
| `channelId` | `string` | Form, Required | The channel that the users will be invited to. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsInviteSchema`](../../doc/models/admin-conversations-invite-schema.md).

## Example Usage

```ts
const token = 'token6';

const userIds = 'user_ids4';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsInvite(
    token,
    userIds,
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
    if (error instanceof AdminConversationsInviteErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsInviteErrorSchemaError`](../../doc/models/admin-conversations-invite-error-schema-error.md) |


# Admin Conversations Rename

Rename a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.rename](https://api.slack.com/methods/admin.conversations.rename)

```ts
async adminConversationsRename(
  token: string,
  channelId: string,
  name: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsRenameSchema1>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to rename. |
| `name` | `string` | Form, Required | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsRenameSchema1`](../../doc/models/admin-conversations-rename-schema-1.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

const name = 'name0';

try {
  const response = await adminConversationsApi.adminConversationsRename(
    token,
    channelId,
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
    if (error instanceof AdminConversationsUnarchiveErrorSchema2Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema2Error`](../../doc/models/admin-conversations-unarchive-error-schema-2-error.md) |


# Admin Conversations Search

Search for public or private channels in an Enterprise organization.

API method documentation: [https://api.slack.com/methods/admin.conversations.search](https://api.slack.com/methods/admin.conversations.search)

```ts
async adminConversationsSearch(
  token: string,
  teamIds?: string,
  query?: string,
  limit?: number,
  cursor?: string,
  searchChannelTypes?: string,
  sort?: string,
  sortDir?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsSearchSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `teamIds` | `string \| undefined` | Query, Optional | Comma separated string of team IDs, signifying the workspaces to search through. |
| `query` | `string \| undefined` | Query, Optional | Name of the the channel to query by. |
| `limit` | `number \| undefined` | Query, Optional | Maximum number of items to be returned. Must be between 1 - 20 both inclusive. Default is 10. |
| `cursor` | `string \| undefined` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
| `searchChannelTypes` | `string \| undefined` | Query, Optional | The type of channel to include or exclude in the search. For example `private` will search private channels, while `private_exclude` will exclude them. For a full list of types, check the [Types section](#types). |
| `sort` | `string \| undefined` | Query, Optional | Possible values are `relevant` (search ranking based on what we think is closest), `name` (alphabetical), `member_count` (number of users in the channel), and `created` (date channel was created). You can optionally pair this with the `sort_dir` arg to change how it is sorted |
| `sortDir` | `string \| undefined` | Query, Optional | Sort direction. Possible values are `asc` for ascending order like (1, 2, 3) or (a, b, c), and `desc` for descending order like (3, 2, 1) or (c, b, a) |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsSearchSchema`](../../doc/models/admin-conversations-search-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await adminConversationsApi.adminConversationsSearch(token);

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
    if (error instanceof AdminConversationsSearchErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsSearchErrorSchemaError`](../../doc/models/admin-conversations-search-error-schema-error.md) |


# Admin Conversations Set Conversation Prefs

Set the posting permissions for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setConversationPrefs](https://api.slack.com/methods/admin.conversations.setConversationPrefs)

```ts
async adminConversationsSetConversationPrefs(
  token: string,
  channelId: string,
  prefs: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsSetConversationPrefsSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to set the prefs for |
| `prefs` | `string` | Form, Required | The prefs for this channel in a stringified JSON format. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsSetConversationPrefsSchema`](../../doc/models/admin-conversations-set-conversation-prefs-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

const prefs = 'prefs0';

try {
  const response = await adminConversationsApi.adminConversationsSetConversationPrefs(
    token,
    channelId,
    prefs
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
    if (error instanceof AdminConversationsSetConversationPrefsErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsSetConversationPrefsErrorSchemaError`](../../doc/models/admin-conversations-set-conversation-prefs-error-schema-error.md) |


# Admin Conversations Set Teams

Set the workspaces in an Enterprise grid org that connect to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setTeams](https://api.slack.com/methods/admin.conversations.setTeams)

```ts
async adminConversationsSetTeams(
  token: string,
  channelId: string,
  teamId?: string,
  targetTeamIds?: string,
  orgChannel?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The encoded `channel_id` to add or remove to workspaces. |
| `teamId` | `string \| undefined` | Form, Optional | The workspace to which the channel belongs. Omit this argument if the channel is a cross-workspace shared channel. |
| `targetTeamIds` | `string \| undefined` | Form, Optional | A comma-separated list of workspaces to which the channel should be shared. Not required if the channel is being shared org-wide. |
| `orgChannel` | `boolean \| undefined` | Form, Optional | True if channel has to be converted to an org channel |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsSetTeams(
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


# Admin Conversations Unarchive

Unarchive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.unarchive](https://api.slack.com/methods/admin.conversations.unarchive)

```ts
async adminConversationsUnarchive(
  token: string,
  channelId: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<AdminConversationsUnarchiveSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `string` | Form, Required | The channel to unarchive. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`AdminConversationsUnarchiveSchema`](../../doc/models/admin-conversations-unarchive-schema.md).

## Example Usage

```ts
const token = 'token6';

const channelId = 'channel_id4';

try {
  const response = await adminConversationsApi.adminConversationsUnarchive(
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
    if (error instanceof AdminConversationsUnarchiveErrorSchema3Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema3Error`](../../doc/models/admin-conversations-unarchive-error-schema-3-error.md) |

