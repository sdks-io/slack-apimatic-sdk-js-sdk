# Views

```ts
const viewsApi = new ViewsApi(client);
```

## Class Name

`ViewsApi`

## Methods

* [Views Open](../../doc/controllers/views.md#views-open)
* [Views Publish](../../doc/controllers/views.md#views-publish)
* [Views Push](../../doc/controllers/views.md#views-push)
* [Views Update](../../doc/controllers/views.md#views-update)


# Views Open

Open a view for a user.

API method documentation: [https://api.slack.com/methods/views.open](https://api.slack.com/methods/views.open)

```ts
async viewsOpen(
  token: string,
  triggerId: string,
  view: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `triggerId` | `string` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `string` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const triggerId = 'trigger_id6';

const view = 'view2';

try {
  const response = await viewsApi.viewsOpen(
    token,
    triggerId,
    view
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
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |


# Views Publish

Publish a static view for a User.

API method documentation: [https://api.slack.com/methods/views.publish](https://api.slack.com/methods/views.publish)

```ts
async viewsPublish(
  token: string,
  userId: string,
  view: string,
  hash?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `userId` | `string` | Query, Required | `id` of the user you want publish a view to. |
| `view` | `string` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `string \| undefined` | Query, Optional | A string that represents view state to protect against possible race conditions. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const userId = 'user_id8';

const view = 'view2';

try {
  const response = await viewsApi.viewsPublish(
    token,
    userId,
    view
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
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |


# Views Push

Push a view onto the stack of a root view.

API method documentation: [https://api.slack.com/methods/views.push](https://api.slack.com/methods/views.push)

```ts
async viewsPush(
  token: string,
  triggerId: string,
  view: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `triggerId` | `string` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `string` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const triggerId = 'trigger_id6';

const view = 'view2';

try {
  const response = await viewsApi.viewsPush(
    token,
    triggerId,
    view
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
| Default | Typical error response. | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |


# Views Update

Update an existing view.

API method documentation: [https://api.slack.com/methods/views.update](https://api.slack.com/methods/views.update)

```ts
async viewsUpdate(
  token: string,
  viewId?: string,
  externalId?: string,
  view?: string,
  hash?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `none` |
| `viewId` | `string \| undefined` | Query, Optional | A unique identifier of the view to be updated. Either `view_id` or `external_id` is required. |
| `externalId` | `string \| undefined` | Query, Optional | A unique identifier of the view set by the developer. Must be unique for all views on a team. Max length of 255 characters. Either `view_id` or `external_id` is required. |
| `view` | `string \| undefined` | Query, Optional | A [view object](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `string \| undefined` | Query, Optional | A string that represents view state to protect against possible race conditions. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await viewsApi.viewsUpdate(token);

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
| Default | Typical error response. | [`DefaultErrorTemplateError`](../../doc/models/default-error-template-error.md) |

