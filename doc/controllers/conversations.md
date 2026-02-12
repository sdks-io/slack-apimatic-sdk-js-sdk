# Conversations

```ts
const conversationsApi = new ConversationsApi(client);
```

## Class Name

`ConversationsApi`

## Methods

* [Conversations Archive](../../doc/controllers/conversations.md#conversations-archive)
* [Conversations Close](../../doc/controllers/conversations.md#conversations-close)
* [Conversations Create](../../doc/controllers/conversations.md#conversations-create)
* [Conversations History](../../doc/controllers/conversations.md#conversations-history)
* [Conversations Info](../../doc/controllers/conversations.md#conversations-info)
* [Conversations Invite](../../doc/controllers/conversations.md#conversations-invite)
* [Conversations Join](../../doc/controllers/conversations.md#conversations-join)
* [Conversations Kick](../../doc/controllers/conversations.md#conversations-kick)
* [Conversations Leave](../../doc/controllers/conversations.md#conversations-leave)
* [Conversations List](../../doc/controllers/conversations.md#conversations-list)
* [Conversations Mark](../../doc/controllers/conversations.md#conversations-mark)
* [Conversations Members](../../doc/controllers/conversations.md#conversations-members)
* [Conversations Open](../../doc/controllers/conversations.md#conversations-open)
* [Conversations Rename](../../doc/controllers/conversations.md#conversations-rename)
* [Conversations Replies](../../doc/controllers/conversations.md#conversations-replies)
* [Conversations Set Purpose](../../doc/controllers/conversations.md#conversations-set-purpose)
* [Conversations Set Topic](../../doc/controllers/conversations.md#conversations-set-topic)
* [Conversations Unarchive](../../doc/controllers/conversations.md#conversations-unarchive)


# Conversations Archive

Archives a conversation.

API method documentation: [https://api.slack.com/methods/conversations.archive](https://api.slack.com/methods/conversations.archive)

```ts
async conversationsArchive(
  token?: string,
  channel?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsArchiveSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | ID of conversation to archive |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsArchiveSuccessSchema`](../../doc/models/conversations-archive-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsArchive();

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
    if (error instanceof ConversationsArchiveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsArchiveErrorSchemaError`](../../doc/models/conversations-archive-error-schema-error.md) |


# Conversations Close

Closes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.close](https://api.slack.com/methods/conversations.close)

```ts
async conversationsClose(
  token?: string,
  channel?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsCloseSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | Conversation to close. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsCloseSuccessSchema`](../../doc/models/conversations-close-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsClose();

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
    if (error instanceof ConversationsCloseErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsCloseErrorSchemaError`](../../doc/models/conversations-close-error-schema-error.md) |


# Conversations Create

Initiates a public or private channel-based conversation

API method documentation: [https://api.slack.com/methods/conversations.create](https://api.slack.com/methods/conversations.create)

```ts
async conversationsCreate(
  token?: string,
  name?: string,
  isPrivate?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsCreateSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `name` | `string \| undefined` | Form, Optional | Name of the public or private channel to create |
| `isPrivate` | `boolean \| undefined` | Form, Optional | Create a private channel instead of a public one |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsCreateSuccessSchema`](../../doc/models/conversations-create-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsCreate();

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
    if (error instanceof ConversationsCreateErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when name already in use | [`ConversationsCreateErrorSchemaError`](../../doc/models/conversations-create-error-schema-error.md) |


# Conversations History

Fetches a conversation's history of messages and events.

API method documentation: [https://api.slack.com/methods/conversations.history](https://api.slack.com/methods/conversations.history)

```ts
async conversationsHistory(
  token?: string,
  channel?: string,
  latest?: number,
  oldest?: number,
  inclusive?: boolean,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsHistorySuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `string \| undefined` | Query, Optional | Conversation ID to fetch history for. |
| `latest` | `number \| undefined` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `number \| undefined` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `boolean \| undefined` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsHistorySuccessSchema`](../../doc/models/conversations-history-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsHistory();

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
    if (error instanceof ConversationsHistoryErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsHistoryErrorSchemaError`](../../doc/models/conversations-history-error-schema-error.md) |


# Conversations Info

Retrieve information about a conversation.

API method documentation: [https://api.slack.com/methods/conversations.info](https://api.slack.com/methods/conversations.info)

```ts
async conversationsInfo(
  token?: string,
  channel?: string,
  includeLocale?: boolean,
  includeNumMembers?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsInfoSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `string \| undefined` | Query, Optional | Conversation ID to learn more about |
| `includeLocale` | `boolean \| undefined` | Query, Optional | Set this to `true` to receive the locale for this conversation. Defaults to `false` |
| `includeNumMembers` | `boolean \| undefined` | Query, Optional | Set to `true` to include the member count for the specified conversation. Defaults to `false` |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsInfoSuccessSchema`](../../doc/models/conversations-info-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsInfo();

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
    if (error instanceof ConversationsInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when a channel cannot be found | [`ConversationsInfoErrorSchemaError`](../../doc/models/conversations-info-error-schema-error.md) |


# Conversations Invite

Invites users to a channel.

API method documentation: [https://api.slack.com/methods/conversations.invite](https://api.slack.com/methods/conversations.invite)

```ts
async conversationsInvite(
  token?: string,
  channel?: string,
  users?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsInviteErrorSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | The ID of the public or private channel to invite user(s) to. |
| `users` | `string \| undefined` | Form, Optional | A comma separated list of user IDs. Up to 1000 users may be listed. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsInviteErrorSchema`](../../doc/models/conversations-invite-error-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsInvite();

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
    if (error instanceof ConversationsInviteErrorSchema1Error) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when an invite is attempted on a conversation type that does not support it | [`ConversationsInviteErrorSchema1Error`](../../doc/models/conversations-invite-error-schema-1-error.md) |


# Conversations Join

Joins an existing conversation.

API method documentation: [https://api.slack.com/methods/conversations.join](https://api.slack.com/methods/conversations.join)

```ts
async conversationsJoin(
  token?: string,
  channel?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsJoinSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `channels:write` |
| `channel` | `string \| undefined` | Form, Optional | ID of conversation to join |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsJoinSuccessSchema`](../../doc/models/conversations-join-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsJoin();

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
    if (error instanceof ConversationsJoinErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the conversation is archived and cannot be joined | [`ConversationsJoinErrorSchemaError`](../../doc/models/conversations-join-error-schema-error.md) |


# Conversations Kick

Removes a user from a conversation.

API method documentation: [https://api.slack.com/methods/conversations.kick](https://api.slack.com/methods/conversations.kick)

```ts
async conversationsKick(
  token?: string,
  channel?: string,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsKickSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | ID of conversation to remove user from. |
| `user` | `string \| undefined` | Form, Optional | User ID to be removed. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsKickSuccessSchema`](../../doc/models/conversations-kick-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsKick();

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
    if (error instanceof ConversationsKickErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when you attempt to kick yourself from a channel | [`ConversationsKickErrorSchemaError`](../../doc/models/conversations-kick-error-schema-error.md) |


# Conversations Leave

Leaves a conversation.

API method documentation: [https://api.slack.com/methods/conversations.leave](https://api.slack.com/methods/conversations.leave)

```ts
async conversationsLeave(
  token?: string,
  channel?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsLeaveSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | Conversation to leave |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsLeaveSuccessSchema`](../../doc/models/conversations-leave-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsLeave();

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
    if (error instanceof ConversationsLeaveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when attempting to leave a workspace's "general" channel | [`ConversationsLeaveErrorSchemaError`](../../doc/models/conversations-leave-error-schema-error.md) |


# Conversations List

Lists all channels in a Slack team.

API method documentation: [https://api.slack.com/methods/conversations.list](https://api.slack.com/methods/conversations.list)

```ts
async conversationsList(
  token?: string,
  excludeArchived?: boolean,
  types?: string,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsListSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `excludeArchived` | `boolean \| undefined` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `types` | `string \| undefined` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsListSuccessSchema`](../../doc/models/conversations-list-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsList();

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
    if (error instanceof ConversationsListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsListErrorSchemaError`](../../doc/models/conversations-list-error-schema-error.md) |


# Conversations Mark

Sets the read cursor in a channel.

API method documentation: [https://api.slack.com/methods/conversations.mark](https://api.slack.com/methods/conversations.mark)

```ts
async conversationsMark(
  token?: string,
  channel?: string,
  ts?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsMarkSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | Channel or conversation to set the read cursor for. |
| `ts` | `number \| undefined` | Form, Optional | Unique identifier of message you want marked as most recently seen in this conversation. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsMarkSuccessSchema`](../../doc/models/conversations-mark-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsMark();

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
    if (error instanceof ConversationsMarkErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsMarkErrorSchemaError`](../../doc/models/conversations-mark-error-schema-error.md) |


# Conversations Members

Retrieve members of a conversation.

API method documentation: [https://api.slack.com/methods/conversations.members](https://api.slack.com/methods/conversations.members)

```ts
async conversationsMembers(
  token?: string,
  channel?: string,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsMembersSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `string \| undefined` | Query, Optional | ID of the conversation to retrieve members for |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsMembersSuccessSchema`](../../doc/models/conversations-members-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsMembers();

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
    if (error instanceof ConversationsMembersErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when an invalid cursor is provided | [`ConversationsMembersErrorSchemaError`](../../doc/models/conversations-members-error-schema-error.md) |


# Conversations Open

Opens or resumes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.open](https://api.slack.com/methods/conversations.open)

```ts
async conversationsOpen(
  token?: string,
  channel?: string,
  users?: string,
  returnIm?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsOpenSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | Resume a conversation by supplying an `im` or `mpim`'s ID. Or provide the `users` field instead. |
| `users` | `string \| undefined` | Form, Optional | Comma separated lists of users. If only one user is included, this creates a 1:1 DM.  The ordering of the users is preserved whenever a multi-person direct message is returned. Supply a `channel` when not supplying `users`. |
| `returnIm` | `boolean \| undefined` | Form, Optional | Boolean, indicates you want the full IM channel definition in the response. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsOpenSuccessSchema`](../../doc/models/conversations-open-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsOpen();

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
    if (error instanceof ConversationsOpenErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsOpenErrorSchemaError`](../../doc/models/conversations-open-error-schema-error.md) |


# Conversations Rename

Renames a conversation.

API method documentation: [https://api.slack.com/methods/conversations.rename](https://api.slack.com/methods/conversations.rename)

```ts
async conversationsRename(
  token?: string,
  channel?: string,
  name?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsRenameSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | ID of conversation to rename |
| `name` | `string \| undefined` | Form, Optional | New name for conversation. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsRenameSuccessSchema`](../../doc/models/conversations-rename-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsRename();

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
    if (error instanceof ConversationsRenameErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when the calling user is not a member of the conversation | [`ConversationsRenameErrorSchemaError`](../../doc/models/conversations-rename-error-schema-error.md) |


# Conversations Replies

Retrieve a thread of messages posted to a conversation

API method documentation: [https://api.slack.com/methods/conversations.replies](https://api.slack.com/methods/conversations.replies)

```ts
async conversationsReplies(
  token?: string,
  channel?: string,
  ts?: number,
  latest?: number,
  oldest?: number,
  inclusive?: boolean,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsRepliesSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `string \| undefined` | Query, Optional | Conversation ID to fetch thread from. |
| `ts` | `number \| undefined` | Query, Optional | Unique identifier of a thread's parent message. `ts` must be the timestamp of an existing message with 0 or more replies. If there are no replies then just the single message referenced by `ts` will return - it is just an ordinary, unthreaded message. |
| `latest` | `number \| undefined` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `number \| undefined` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `boolean \| undefined` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsRepliesSuccessSchema`](../../doc/models/conversations-replies-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsReplies();

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
    if (error instanceof ConversationsRepliesErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsRepliesErrorSchemaError`](../../doc/models/conversations-replies-error-schema-error.md) |


# Conversations Set Purpose

Sets the purpose for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setPurpose](https://api.slack.com/methods/conversations.setPurpose)

```ts
async conversationsSetPurpose(
  token?: string,
  channel?: string,
  purpose?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsSetPurposeSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | Conversation to set the purpose of |
| `purpose` | `string \| undefined` | Form, Optional | A new, specialer purpose |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsSetPurposeSuccessSchema`](../../doc/models/conversations-set-purpose-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsSetPurpose();

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
    if (error instanceof ConversationsSetPurposeErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsSetPurposeErrorSchemaError`](../../doc/models/conversations-set-purpose-error-schema-error.md) |


# Conversations Set Topic

Sets the topic for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setTopic](https://api.slack.com/methods/conversations.setTopic)

```ts
async conversationsSetTopic(
  token?: string,
  channel?: string,
  topic?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsSetTopicSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | Conversation to set the topic of |
| `topic` | `string \| undefined` | Form, Optional | The new topic string. Does not support formatting or linkification. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsSetTopicSuccessSchema`](../../doc/models/conversations-set-topic-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsSetTopic();

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
    if (error instanceof ConversationsSetTopicErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsSetTopicErrorSchemaError`](../../doc/models/conversations-set-topic-error-schema-error.md) |


# Conversations Unarchive

Reverses conversation archival.

API method documentation: [https://api.slack.com/methods/conversations.unarchive](https://api.slack.com/methods/conversations.unarchive)

```ts
async conversationsUnarchive(
  token?: string,
  channel?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ConversationsUnarchiveSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `string \| undefined` | Form, Optional | ID of conversation to unarchive |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ConversationsUnarchiveSuccessSchema`](../../doc/models/conversations-unarchive-success-schema.md).

## Example Usage

```ts
try {
  const response = await conversationsApi.conversationsUnarchive();

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
    if (error instanceof ConversationsUnarchiveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ConversationsUnarchiveErrorSchemaError`](../../doc/models/conversations-unarchive-error-schema-error.md) |

