# Files Remote

```ts
const filesRemoteApi = new FilesRemoteApi(client);
```

## Class Name

`FilesRemoteApi`

## Methods

* [Files Remote Add](../../doc/controllers/files-remote.md#files-remote-add)
* [Files Remote Info](../../doc/controllers/files-remote.md#files-remote-info)
* [Files Remote List](../../doc/controllers/files-remote.md#files-remote-list)
* [Files Remote Remove](../../doc/controllers/files-remote.md#files-remote-remove)
* [Files Remote Share](../../doc/controllers/files-remote.md#files-remote-share)
* [Files Remote Update](../../doc/controllers/files-remote.md#files-remote-update)


# Files Remote Add

Adds a file from a remote service

API method documentation: [https://api.slack.com/methods/files.remote.add](https://api.slack.com/methods/files.remote.add)

```ts
async filesRemoteAdd(
  token?: string,
  externalId?: string,
  title?: string,
  filetype?: string,
  externalUrl?: string,
  previewImage?: string,
  indexableFileContents?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `externalId` | `string \| undefined` | Form, Optional | Creator defined GUID for the file. |
| `title` | `string \| undefined` | Form, Optional | Title of the file being shared. |
| `filetype` | `string \| undefined` | Form, Optional | type of file |
| `externalUrl` | `string \| undefined` | Form, Optional | URL of the remote file. |
| `previewImage` | `string \| undefined` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexableFileContents` | `string \| undefined` | Form, Optional | A text file (txt, pdf, doc, etc.) containing textual search terms that are used to improve discovery of the remote file. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await filesRemoteApi.filesRemoteAdd();

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


# Files Remote Info

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.info](https://api.slack.com/methods/files.remote.info)

```ts
async filesRemoteInfo(
  token?: string,
  file?: string,
  externalId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `file` | `string \| undefined` | Query, Optional | Specify a file by providing its ID. |
| `externalId` | `string \| undefined` | Query, Optional | Creator defined GUID for the file. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await filesRemoteApi.filesRemoteInfo();

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


# Files Remote List

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.list](https://api.slack.com/methods/files.remote.list)

```ts
async filesRemoteList(
  token?: string,
  channel?: string,
  tsFrom?: number,
  tsTo?: number,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `channel` | `string \| undefined` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `tsFrom` | `number \| undefined` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `tsTo` | `number \| undefined` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. |
| `cursor` | `string \| undefined` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await filesRemoteApi.filesRemoteList();

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


# Files Remote Remove

Remove a remote file.

API method documentation: [https://api.slack.com/methods/files.remote.remove](https://api.slack.com/methods/files.remote.remove)

```ts
async filesRemoteRemove(
  token?: string,
  file?: string,
  externalId?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `string \| undefined` | Form, Optional | Specify a file by providing its ID. |
| `externalId` | `string \| undefined` | Form, Optional | Creator defined GUID for the file. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await filesRemoteApi.filesRemoteRemove();

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


# Files Remote Share

Share a remote file into a channel.

API method documentation: [https://api.slack.com/methods/files.remote.share](https://api.slack.com/methods/files.remote.share)

```ts
async filesRemoteShare(
  token?: string,
  file?: string,
  externalId?: string,
  channels?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `remote_files:share` |
| `file` | `string \| undefined` | Query, Optional | Specify a file registered with Slack by providing its ID. Either this field or `external_id` or both are required. |
| `externalId` | `string \| undefined` | Query, Optional | The globally unique identifier (GUID) for the file, as set by the app registering the file with Slack.  Either this field or `file` or both are required. |
| `channels` | `string \| undefined` | Query, Optional | Comma-separated list of channel IDs where the file will be shared. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`remote_files:share`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await filesRemoteApi.filesRemoteShare();

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


# Files Remote Update

Updates an existing remote file.

API method documentation: [https://api.slack.com/methods/files.remote.update](https://api.slack.com/methods/files.remote.update)

```ts
async filesRemoteUpdate(
  token?: string,
  file?: string,
  externalId?: string,
  title?: string,
  filetype?: string,
  externalUrl?: string,
  previewImage?: string,
  indexableFileContents?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `string \| undefined` | Form, Optional | Specify a file by providing its ID. |
| `externalId` | `string \| undefined` | Form, Optional | Creator defined GUID for the file. |
| `title` | `string \| undefined` | Form, Optional | Title of the file being shared. |
| `filetype` | `string \| undefined` | Form, Optional | type of file |
| `externalUrl` | `string \| undefined` | Form, Optional | URL of the remote file. |
| `previewImage` | `string \| undefined` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexableFileContents` | `string \| undefined` | Form, Optional | File containing contents that can be used to improve searchability for the remote file. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
try {
  const response = await filesRemoteApi.filesRemoteUpdate();

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

