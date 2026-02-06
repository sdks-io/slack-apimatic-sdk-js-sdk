# Chat

```ts
const chatApi = new ChatApi(client);
```

## Class Name

`ChatApi`

## Methods

* [Chat Delete](../../doc/controllers/chat.md#chat-delete)
* [Chat Delete Scheduled Message](../../doc/controllers/chat.md#chat-delete-scheduled-message)
* [Chat Get Permalink](../../doc/controllers/chat.md#chat-get-permalink)
* [Chat Me Message](../../doc/controllers/chat.md#chat-me-message)
* [Chat Post Ephemeral](../../doc/controllers/chat.md#chat-post-ephemeral)
* [Chat Post Message](../../doc/controllers/chat.md#chat-post-message)
* [Chat Schedule Message](../../doc/controllers/chat.md#chat-schedule-message)
* [Chat Unfurl](../../doc/controllers/chat.md#chat-unfurl)
* [Chat Update](../../doc/controllers/chat.md#chat-update)


# Chat Delete

Deletes a message.

API method documentation: [https://api.slack.com/methods/chat.delete](https://api.slack.com/methods/chat.delete)

```ts
async chatDelete(
  token?: string,
  ts?: number,
  channel?: string,
  asUser?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatDeleteSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `ts` | `number \| undefined` | Form, Optional | Timestamp of the message to be deleted. |
| `channel` | `string \| undefined` | Form, Optional | Channel containing the message to be deleted. |
| `asUser` | `boolean \| undefined` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatDeleteSuccessSchema`](../../doc/models/chat-delete-success-schema.md).

## Example Usage

```ts
try {
  const response = await chatApi.chatDelete();

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
    if (error instanceof ChatDeleteErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatDeleteErrorSchemaError`](../../doc/models/chat-delete-error-schema-error.md) |


# Chat Delete Scheduled Message

Deletes a pending scheduled message from the queue.

API method documentation: [https://api.slack.com/methods/chat.deleteScheduledMessage](https://api.slack.com/methods/chat.deleteScheduledMessage)

```ts
async chatDeleteScheduledMessage(
  token: string,
  channel: string,
  scheduledMessageId: string,
  asUser?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatDeleteScheduledMessageSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | The channel the scheduled_message is posting to |
| `scheduledMessageId` | `string` | Form, Required | `scheduled_message_id` returned from call to chat.scheduleMessage |
| `asUser` | `boolean \| undefined` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatDeleteScheduledMessageSchema`](../../doc/models/chat-delete-scheduled-message-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

const scheduledMessageId = 'scheduled_message_id8';

try {
  const response = await chatApi.chatDeleteScheduledMessage(
    token,
    channel,
    scheduledMessageId
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
    if (error instanceof ChatDeleteScheduledMessageErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if no message is found | [`ChatDeleteScheduledMessageErrorSchemaError`](../../doc/models/chat-delete-scheduled-message-error-schema-error.md) |


# Chat Get Permalink

Retrieve a permalink URL for a specific extant message

API method documentation: [https://api.slack.com/methods/chat.getPermalink](https://api.slack.com/methods/chat.getPermalink)

```ts
async chatGetPermalink(
  token: string,
  channel: string,
  messageTs: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatGetPermalinkSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `none` |
| `channel` | `string` | Query, Required | The ID of the conversation or channel containing the message |
| `messageTs` | `string` | Query, Required | A message's `ts` value, uniquely identifying it within a channel |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatGetPermalinkSuccessSchema`](../../doc/models/chat-get-permalink-success-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

const messageTs = 'message_ts4';

try {
  const response = await chatApi.chatGetPermalink(
    token,
    channel,
    messageTs
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
    if (error instanceof ChatGetPermalinkErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Error response when channel cannot be found | [`ChatGetPermalinkErrorSchemaError`](../../doc/models/chat-get-permalink-error-schema-error.md) |


# Chat Me Message

Share a me message into a channel.

API method documentation: [https://api.slack.com/methods/chat.meMessage](https://api.slack.com/methods/chat.meMessage)

```ts
async chatMeMessage(
  token?: string,
  channel?: string,
  text?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatMeMessageSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `string \| undefined` | Form, Optional | Channel to send message to. Can be a public channel, private group or IM channel. Can be an encoded ID, or a name. |
| `text` | `string \| undefined` | Form, Optional | Text of the message to send. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatMeMessageSchema`](../../doc/models/chat-me-message-schema.md).

## Example Usage

```ts
try {
  const response = await chatApi.chatMeMessage();

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
    if (error instanceof ChatMeMessageErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatMeMessageErrorSchemaError`](../../doc/models/chat-me-message-error-schema-error.md) |


# Chat Post Ephemeral

Sends an ephemeral message to a user in a channel.

API method documentation: [https://api.slack.com/methods/chat.postEphemeral](https://api.slack.com/methods/chat.postEphemeral)

```ts
async chatPostEphemeral(
  token: string,
  channel: string,
  user: string,
  asUser?: boolean,
  attachments?: string,
  blocks?: string,
  iconEmoji?: string,
  iconUrl?: string,
  linkNames?: boolean,
  parse?: string,
  text?: string,
  threadTs?: string,
  username?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatPostEphemeralSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. |
| `user` | `string` | Form, Required | `id` of the user who will receive the ephemeral message. The user should be in the channel specified by the `channel` argument. |
| `asUser` | `boolean \| undefined` | Form, Optional | Pass true to post the message as the authed user. Defaults to true if the chat:write:bot scope is not included. Otherwise, defaults to false. |
| `attachments` | `string \| undefined` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `string \| undefined` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `iconEmoji` | `string \| undefined` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `iconUrl` | `string \| undefined` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `linkNames` | `boolean \| undefined` | Form, Optional | Find and link channel names and usernames. |
| `parse` | `string \| undefined` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `text` | `string \| undefined` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `threadTs` | `string \| undefined` | Form, Optional | Provide another message's `ts` value to post this message in a thread. Avoid using a reply's `ts` value; use its parent's value instead. Ephemeral messages in threads are only shown if there is already an active thread. |
| `username` | `string \| undefined` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatPostEphemeralSuccessSchema`](../../doc/models/chat-post-ephemeral-success-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

const user = 'user0';

try {
  const response = await chatApi.chatPostEphemeral(
    token,
    channel,
    user
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
    if (error instanceof ChatPostEphemeralErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatPostEphemeralErrorSchemaError`](../../doc/models/chat-post-ephemeral-error-schema-error.md) |


# Chat Post Message

Sends a message to a channel.

API method documentation: [https://api.slack.com/methods/chat.postMessage](https://api.slack.com/methods/chat.postMessage)

```ts
async chatPostMessage(
  token: string,
  channel: string,
  asUser?: string,
  attachments?: string,
  blocks?: string,
  iconEmoji?: string,
  iconUrl?: string,
  linkNames?: boolean,
  mrkdwn?: boolean,
  parse?: string,
  replyBroadcast?: boolean,
  text?: string,
  threadTs?: string,
  unfurlLinks?: boolean,
  unfurlMedia?: boolean,
  username?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatPostMessageSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `asUser` | `string \| undefined` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [authorship](#authorship) below. |
| `attachments` | `string \| undefined` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `string \| undefined` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `iconEmoji` | `string \| undefined` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `iconUrl` | `string \| undefined` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `linkNames` | `boolean \| undefined` | Form, Optional | Find and link channel names and usernames. |
| `mrkdwn` | `boolean \| undefined` | Form, Optional | Disable Slack markup parsing by setting to `false`. Enabled by default. |
| `parse` | `string \| undefined` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `replyBroadcast` | `boolean \| undefined` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |
| `text` | `string \| undefined` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `threadTs` | `string \| undefined` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `unfurlLinks` | `boolean \| undefined` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurlMedia` | `boolean \| undefined` | Form, Optional | Pass false to disable unfurling of media content. |
| `username` | `string \| undefined` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatPostMessageSuccessSchema`](../../doc/models/chat-post-message-success-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

try {
  const response = await chatApi.chatPostMessage(
    token,
    channel
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
    if (error instanceof ChatPostMessageErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if too many attachments are included | [`ChatPostMessageErrorSchemaError`](../../doc/models/chat-post-message-error-schema-error.md) |


# Chat Schedule Message

Schedules a message to be sent to a channel.

API method documentation: [https://api.slack.com/methods/chat.scheduleMessage](https://api.slack.com/methods/chat.scheduleMessage)

```ts
async chatScheduleMessage(
  token?: string,
  channel?: string,
  text?: string,
  postAt?: string,
  parse?: string,
  asUser?: boolean,
  linkNames?: boolean,
  attachments?: string,
  blocks?: string,
  unfurlLinks?: boolean,
  unfurlMedia?: boolean,
  threadTs?: number,
  replyBroadcast?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatScheduleMessageSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `string \| undefined` | Form, Optional | Channel, private group, or DM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `text` | `string \| undefined` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `postAt` | `string \| undefined` | Form, Optional | Unix EPOCH timestamp of time in future to send the message. |
| `parse` | `string \| undefined` | Form, Optional | Change how messages are treated. Defaults to `none`. See [chat.postMessage](chat.postMessage#formatting). |
| `asUser` | `boolean \| undefined` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [chat.postMessage](chat.postMessage#authorship). |
| `linkNames` | `boolean \| undefined` | Form, Optional | Find and link channel names and usernames. |
| `attachments` | `string \| undefined` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `string \| undefined` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `unfurlLinks` | `boolean \| undefined` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurlMedia` | `boolean \| undefined` | Form, Optional | Pass false to disable unfurling of media content. |
| `threadTs` | `number \| undefined` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `replyBroadcast` | `boolean \| undefined` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatScheduleMessageSuccessSchema`](../../doc/models/chat-schedule-message-success-schema.md).

## Example Usage

```ts
try {
  const response = await chatApi.chatScheduleMessage();

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
    if (error instanceof ChatScheduleMessageErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the `post_at` is invalid (ex. in the past or too far into the future) | [`ChatScheduleMessageErrorSchemaError`](../../doc/models/chat-schedule-message-error-schema-error.md) |


# Chat Unfurl

Provide custom unfurl behavior for user-posted URLs

API method documentation: [https://api.slack.com/methods/chat.unfurl](https://api.slack.com/methods/chat.unfurl)

```ts
async chatUnfurl(
  token: string,
  channel: string,
  ts: string,
  unfurls?: string,
  userAuthMessage?: string,
  userAuthRequired?: boolean,
  userAuthUrl?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatUnfurlSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `links:write` |
| `channel` | `string` | Form, Required | Channel ID of the message |
| `ts` | `string` | Form, Required | Timestamp of the message to add unfurl behavior to. |
| `unfurls` | `string \| undefined` | Form, Optional | URL-encoded JSON map with keys set to URLs featured in the the message, pointing to their unfurl blocks or message attachments. |
| `userAuthMessage` | `string \| undefined` | Form, Optional | Provide a simply-formatted string to send as an ephemeral message to the user as invitation to authenticate further and enable full unfurling behavior |
| `userAuthRequired` | `boolean \| undefined` | Form, Optional | Set to `true` or `1` to indicate the user must install your Slack app to trigger unfurls for this domain |
| `userAuthUrl` | `string \| undefined` | Form, Optional | Send users to this custom URL where they will complete authentication in your app to fully trigger unfurling. Value should be properly URL-encoded. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`links:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatUnfurlSuccessSchema`](../../doc/models/chat-unfurl-success-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

const ts = 'ts2';

try {
  const response = await chatApi.chatUnfurl(
    token,
    channel,
    ts
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
    if (error instanceof ChatUnfurlErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatUnfurlErrorSchemaError`](../../doc/models/chat-unfurl-error-schema-error.md) |


# Chat Update

Updates a message.

API method documentation: [https://api.slack.com/methods/chat.update](https://api.slack.com/methods/chat.update)

```ts
async chatUpdate(
  token: string,
  channel: string,
  ts: string,
  asUser?: string,
  attachments?: string,
  blocks?: string,
  linkNames?: string,
  parse?: string,
  text?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatUpdateSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `string` | Form, Required | Channel containing the message to be updated. |
| `ts` | `string` | Form, Required | Timestamp of the message to be updated. |
| `asUser` | `string \| undefined` | Form, Optional | Pass true to update the message as the authed user. [Bot users](/bot-users) in this context are considered authed users. |
| `attachments` | `string \| undefined` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. This field is required when not presenting `text`. If you don't include this field, the message's previous `attachments` will be retained. To remove previous `attachments`, include an empty array for this field. |
| `blocks` | `string \| undefined` | Form, Optional | A JSON-based array of [structured blocks](/block-kit/building), presented as a URL-encoded string. If you don't include this field, the message's previous `blocks` will be retained. To remove previous `blocks`, include an empty array for this field. |
| `linkNames` | `string \| undefined` | Form, Optional | Find and link channel names and usernames. Defaults to `none`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `none`. |
| `parse` | `string \| undefined` | Form, Optional | Change how messages are treated. Defaults to `client`, unlike `chat.postMessage`. Accepts either `none` or `full`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `client`. |
| `text` | `string \| undefined` | Form, Optional | New text for the message, using the [default formatting rules](/reference/surfaces/formatting). It's not required when presenting `blocks` or `attachments`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatUpdateSuccessSchema`](../../doc/models/chat-update-success-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

const ts = 'ts2';

try {
  const response = await chatApi.chatUpdate(
    token,
    channel,
    ts
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
    if (error instanceof ChatUpdateErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ChatUpdateErrorSchemaError`](../../doc/models/chat-update-error-schema-error.md) |

