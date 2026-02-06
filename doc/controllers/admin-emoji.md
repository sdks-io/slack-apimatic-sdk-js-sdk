# Admin Emoji

```ts
const adminEmojiApi = new AdminEmojiApi(client);
```

## Class Name

`AdminEmojiApi`

## Methods

* [Admin Emoji Add](../../doc/controllers/admin-emoji.md#admin-emoji-add)
* [Admin Emoji Add Alias](../../doc/controllers/admin-emoji.md#admin-emoji-add-alias)
* [Admin Emoji List](../../doc/controllers/admin-emoji.md#admin-emoji-list)
* [Admin Emoji Remove](../../doc/controllers/admin-emoji.md#admin-emoji-remove)
* [Admin Emoji Rename](../../doc/controllers/admin-emoji.md#admin-emoji-rename)


# Admin Emoji Add

Add an emoji.

API method documentation: [https://api.slack.com/methods/admin.emoji.add](https://api.slack.com/methods/admin.emoji.add)

```ts
async adminEmojiAdd(
  token: string,
  name: string,
  url: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be removed. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `url` | `string` | Form, Required | The URL of a file to use as an image for the emoji. Square images under 128KB and with transparent backgrounds work best. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const name = 'name0';

const url = 'url4';

try {
  const response = await adminEmojiApi.adminEmojiAdd(
    token,
    name,
    url
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


# Admin Emoji Add Alias

Add an emoji alias.

API method documentation: [https://api.slack.com/methods/admin.emoji.addAlias](https://api.slack.com/methods/admin.emoji.addAlias)

```ts
async adminEmojiAddAlias(
  token: string,
  name: string,
  aliasFor: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be aliased. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `aliasFor` | `string` | Form, Required | The alias of the emoji. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const name = 'name0';

const aliasFor = 'alias_for4';

try {
  const response = await adminEmojiApi.adminEmojiAddAlias(
    token,
    name,
    aliasFor
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


# Admin Emoji List

List emoji for an Enterprise Grid organization.

API method documentation: [https://api.slack.com/methods/admin.emoji.list](https://api.slack.com/methods/admin.emoji.list)

```ts
async adminEmojiList(
  token: string,
  cursor?: string,
  limit?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin.teams:read` |
| `cursor` | `string \| undefined` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await adminEmojiApi.adminEmojiList(token);

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


# Admin Emoji Remove

Remove an emoji across an Enterprise Grid organization

API method documentation: [https://api.slack.com/methods/admin.emoji.remove](https://api.slack.com/methods/admin.emoji.remove)

```ts
async adminEmojiRemove(
  token: string,
  name: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be removed. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const name = 'name0';

try {
  const response = await adminEmojiApi.adminEmojiRemove(
    token,
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


# Admin Emoji Rename

Rename an emoji.

API method documentation: [https://api.slack.com/methods/admin.emoji.rename](https://api.slack.com/methods/admin.emoji.rename)

```ts
async adminEmojiRename(
  token: string,
  name: string,
  newName: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `string` | Form, Required | The name of the emoji to be renamed. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `newName` | `string` | Form, Required | The new name of the emoji. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const name = 'name0';

const newName = 'new_name8';

try {
  const response = await adminEmojiApi.adminEmojiRename(
    token,
    name,
    newName
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

