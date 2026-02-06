# Pins

```ts
const pinsApi = new PinsApi(client);
```

## Class Name

`PinsApi`

## Methods

* [Pins Add](../../doc/controllers/pins.md#pins-add)
* [Pins List](../../doc/controllers/pins.md#pins-list)
* [Pins Remove](../../doc/controllers/pins.md#pins-remove)


# Pins Add

Pins an item to a channel.

API method documentation: [https://api.slack.com/methods/pins.add](https://api.slack.com/methods/pins.add)

```ts
async pinsAdd(
  token: string,
  channel: string,
  timestamp?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PinsAddSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `pins:write` |
| `channel` | `string` | Form, Required | Channel to pin the item in. |
| `timestamp` | `string \| undefined` | Form, Optional | Timestamp of the message to pin. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`pins:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PinsAddSchema`](../../doc/models/pins-add-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

try {
  const response = await pinsApi.pinsAdd(
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
    if (error instanceof PinsAddErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`PinsAddErrorSchemaError`](../../doc/models/pins-add-error-schema-error.md) |


# Pins List

Lists items pinned to a channel.

API method documentation: [https://api.slack.com/methods/pins.list](https://api.slack.com/methods/pins.list)

```ts
async pinsList(
  token: string,
  channel: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<unknown>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `pins:read` |
| `channel` | `string` | Query, Required | Channel to get pinned items for. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`pins:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type `unknown`.

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

try {
  const response = await pinsApi.pinsList(
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
    if (error instanceof PinsListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Example Response

```
{
  "items": [
    {
      "channel": "C2U86NC6H",
      "created": 1508881078,
      "created_by": "U2U85N1RZ",
      "message": {
        "permalink": "https://hitchhikers.slack.com/archives/C2U86NC6H/p1508197641000151",
        "pinned_to": [
          "C2U86NC6H"
        ],
        "text": "What is the meaning of life?",
        "ts": "1508197641.000151",
        "type": "message",
        "user": "U2U85N1RZ"
      },
      "type": "message"
    },
    {
      "channel": "C2U86NC6H",
      "created": 1508880991,
      "created_by": "U2U85N1RZ",
      "message": {
        "permalink": "https://hitchhikers.slack.com/archives/C2U86NC6H/p1508284197000015",
        "pinned_to": [
          "C2U86NC6H"
        ],
        "text": "The meaning of life, the universe, and everything is 42.",
        "ts": "1503289197.000015",
        "type": "message",
        "user": "U2U85N1RZ"
      },
      "type": "message"
    }
  ],
  "ok": true
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`PinsListErrorSchemaError`](../../doc/models/pins-list-error-schema-error.md) |


# Pins Remove

Un-pins an item from a channel.

API method documentation: [https://api.slack.com/methods/pins.remove](https://api.slack.com/methods/pins.remove)

```ts
async pinsRemove(
  token: string,
  channel: string,
  timestamp?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<PinsRemoveSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `pins:write` |
| `channel` | `string` | Form, Required | Channel where the item is pinned to. |
| `timestamp` | `string \| undefined` | Form, Optional | Timestamp of the message to un-pin. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`pins:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`PinsRemoveSchema`](../../doc/models/pins-remove-schema.md).

## Example Usage

```ts
const token = 'token6';

const channel = 'channel4';

try {
  const response = await pinsApi.pinsRemove(
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
    if (error instanceof PinsRemoveErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`PinsRemoveErrorSchemaError`](../../doc/models/pins-remove-error-schema-error.md) |

