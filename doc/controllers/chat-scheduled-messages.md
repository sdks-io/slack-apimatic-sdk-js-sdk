# Chat Scheduled Messages

```ts
const chatScheduledMessagesApi = new ChatScheduledMessagesApi(client);
```

## Class Name

`ChatScheduledMessagesApi`


# Chat Scheduled Messages List

Returns a list of scheduled messages.

API method documentation: [https://api.slack.com/methods/chat.scheduledMessages.list](https://api.slack.com/methods/chat.scheduledMessages.list)

```ts
async chatScheduledMessagesList(
  token?: string,
  channel?: string,
  latest?: number,
  oldest?: number,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<ChatScheduledMessagesListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `none` |
| `channel` | `string \| undefined` | Query, Optional | The channel of the scheduled messages |
| `latest` | `number \| undefined` | Query, Optional | A UNIX timestamp of the latest value in the time range |
| `oldest` | `number \| undefined` | Query, Optional | A UNIX timestamp of the oldest value in the time range |
| `limit` | `number \| undefined` | Query, Optional | Maximum number of original entries to return. |
| `cursor` | `string \| undefined` | Query, Optional | For pagination purposes, this is the `cursor` value returned from a previous call to `chat.scheduledmessages.list` indicating where you want to start this call from. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`ChatScheduledMessagesListSchema`](../../doc/models/chat-scheduled-messages-list-schema.md).

## Example Usage

```ts
try {
  const response = await chatScheduledMessagesApi.chatScheduledMessagesList();

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
    if (error instanceof ChatScheduledMessagesListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response if the channel passed is invalid | [`ChatScheduledMessagesListErrorSchemaError`](../../doc/models/chat-scheduled-messages-list-error-schema-error.md) |

