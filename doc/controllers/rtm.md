# Rtm

```ts
const rtmApi = new RtmApi(client);
```

## Class Name

`RtmApi`


# Rtm Connect

Starts a Real Time Messaging session.

API method documentation: [https://api.slack.com/methods/rtm.connect](https://api.slack.com/methods/rtm.connect)

```ts
async rtmConnect(
  token: string,
  batchPresenceAware?: boolean,
  presenceSub?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<RtmConnectSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `rtm:stream` |
| `batchPresenceAware` | `boolean \| undefined` | Query, Optional | Batch presence deliveries via subscription. Enabling changes the shape of `presence_change` events. |
| `presenceSub` | `boolean \| undefined` | Query, Optional | Only deliver presence events when requested by subscription |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`rtm:stream`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`RtmConnectSchema`](../../doc/models/rtm-connect-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await rtmApi.rtmConnect(token);

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
    if (error instanceof RtmConnectErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`RtmConnectErrorSchemaError`](../../doc/models/rtm-connect-error-schema-error.md) |

