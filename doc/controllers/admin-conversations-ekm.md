# Admin Conversations Ekm

```ts
const adminConversationsEkmApi = new AdminConversationsEkmApi(client);
```

## Class Name

`AdminConversationsEkmApi`


# Admin Conversations Ekm List Original Connected Channel Info

List all disconnected channels—i.e., channels that were once connected to other workspaces and then disconnected—and the corresponding original channel IDs for key revocation with EKM.

API method documentation: [https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo](https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo)

```ts
async adminConversationsEkmListOriginalConnectedChannelInfo(
  token: string,
  channelIds?: string,
  teamIds?: string,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelIds` | `string \| undefined` | Query, Optional | A comma-separated list of channels to filter to. |
| `teamIds` | `string \| undefined` | Query, Optional | A comma-separated list of the workspaces to which the channels you would like returned belong. |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `string \| undefined` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await adminConversationsEkmApi.adminConversationsEkmListOriginalConnectedChannelInfo(token);

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

