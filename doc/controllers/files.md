# Files

```ts
const filesApi = new FilesApi(client);
```

## Class Name

`FilesApi`

## Methods

* [Files Delete](../../doc/controllers/files.md#files-delete)
* [Files Info](../../doc/controllers/files.md#files-info)
* [Files List](../../doc/controllers/files.md#files-list)
* [Files Revoke Public URL](../../doc/controllers/files.md#files-revoke-public-url)
* [Files Shared Public URL](../../doc/controllers/files.md#files-shared-public-url)
* [Files Upload](../../doc/controllers/files.md#files-upload)


# Files Delete

Deletes a file.

API method documentation: [https://api.slack.com/methods/files.delete](https://api.slack.com/methods/files.delete)

```ts
async filesDelete(
  token?: string,
  file?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FilesDeleteSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string \| undefined` | Form, Optional | ID of file to delete. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FilesDeleteSchema`](../../doc/models/files-delete-schema.md).

## Example Usage

```ts
try {
  const response = await filesApi.filesDelete();

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
    if (error instanceof FilesDeleteErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesDeleteErrorSchemaError`](../../doc/models/files-delete-error-schema-error.md) |


# Files Info

Gets information about a file.

API method documentation: [https://api.slack.com/methods/files.info](https://api.slack.com/methods/files.info)

```ts
async filesInfo(
  token?: string,
  file?: string,
  count?: string,
  page?: string,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FilesInfoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `file` | `string \| undefined` | Query, Optional | Specify a file by providing its ID. |
| `count` | `string \| undefined` | Query, Optional | - |
| `page` | `string \| undefined` | Query, Optional | - |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |
| `cursor` | `string \| undefined` | Query, Optional | Parameter for pagination. File comments are paginated for a single file. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection of comments. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FilesInfoSchema`](../../doc/models/files-info-schema.md).

## Example Usage

```ts
try {
  const response = await filesApi.filesInfo();

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
    if (error instanceof FilesInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesInfoErrorSchemaError`](../../doc/models/files-info-error-schema-error.md) |


# Files List

List for a team, in a channel, or from a user with applied filters.

API method documentation: [https://api.slack.com/methods/files.list](https://api.slack.com/methods/files.list)

```ts
async filesList(
  token?: string,
  user?: string,
  channel?: string,
  tsFrom?: number,
  tsTo?: number,
  types?: string,
  count?: string,
  page?: string,
  showFilesHiddenByLimit?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FilesListSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `user` | `string \| undefined` | Query, Optional | Filter files created by a single user. |
| `channel` | `string \| undefined` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `tsFrom` | `number \| undefined` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `tsTo` | `number \| undefined` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `types` | `string \| undefined` | Query, Optional | Filter files by type ([see below](#file_types)). You can pass multiple values in the types argument, like `types=spaces,snippets`.The default value is `all`, which does not filter the list. |
| `count` | `string \| undefined` | Query, Optional | - |
| `page` | `string \| undefined` | Query, Optional | - |
| `showFilesHiddenByLimit` | `boolean \| undefined` | Query, Optional | Show truncated file info for files hidden due to being too old, and the team who owns the file being over the file limit. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FilesListSchema`](../../doc/models/files-list-schema.md).

## Example Usage

```ts
try {
  const response = await filesApi.filesList();

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
    if (error instanceof FilesListErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesListErrorSchemaError`](../../doc/models/files-list-error-schema-error.md) |


# Files Revoke Public URL

Revokes public/external sharing access for a file

API method documentation: [https://api.slack.com/methods/files.revokePublicURL](https://api.slack.com/methods/files.revokePublicURL)

```ts
async filesRevokePublicUrl(
  token?: string,
  file?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FilesRevokePublicUrlSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string \| undefined` | Form, Optional | File to revoke |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FilesRevokePublicUrlSchema`](../../doc/models/files-revoke-public-url-schema.md).

## Example Usage

```ts
try {
  const response = await filesApi.filesRevokePublicUrl();

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
    if (error instanceof FilesRevokePublicUrlErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesRevokePublicUrlErrorSchemaError`](../../doc/models/files-revoke-public-url-error-schema-error.md) |


# Files Shared Public URL

Enables a file for public/external sharing.

API method documentation: [https://api.slack.com/methods/files.sharedPublicURL](https://api.slack.com/methods/files.sharedPublicURL)

```ts
async filesSharedPublicUrl(
  token?: string,
  file?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FilesSharedPublicUrlSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string \| undefined` | Form, Optional | File to share |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FilesSharedPublicUrlSchema`](../../doc/models/files-shared-public-url-schema.md).

## Example Usage

```ts
try {
  const response = await filesApi.filesSharedPublicUrl();

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
    if (error instanceof FilesSharedPublicUrlErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesSharedPublicUrlErrorSchemaError`](../../doc/models/files-shared-public-url-error-schema-error.md) |


# Files Upload

Uploads or creates a file.

API method documentation: [https://api.slack.com/methods/files.upload](https://api.slack.com/methods/files.upload)

```ts
async filesUpload(
  token?: string,
  file?: string,
  content?: string,
  filetype?: string,
  filename?: string,
  title?: string,
  initialComment?: string,
  channels?: string,
  threadTs?: number,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FilesUploadSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Form, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string \| undefined` | Form, Optional | File contents via `multipart/form-data`. If omitting this parameter, you must submit `content`. |
| `content` | `string \| undefined` | Form, Optional | File contents via a POST variable. If omitting this parameter, you must provide a `file`. |
| `filetype` | `string \| undefined` | Form, Optional | A [file type](/types/file#file_types) identifier. |
| `filename` | `string \| undefined` | Form, Optional | Filename of file. |
| `title` | `string \| undefined` | Form, Optional | Title of file. |
| `initialComment` | `string \| undefined` | Form, Optional | The message text introducing the file in specified `channels`. |
| `channels` | `string \| undefined` | Form, Optional | Comma-separated list of channel names or IDs where the file will be shared. |
| `threadTs` | `number \| undefined` | Form, Optional | Provide another message's `ts` value to upload this file as a reply. Never use a reply's `ts` value; use its parent instead. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FilesUploadSchema`](../../doc/models/files-upload-schema.md).

## Example Usage

```ts
try {
  const response = await filesApi.filesUpload();

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
    if (error instanceof FilesUploadErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`FilesUploadErrorSchemaError`](../../doc/models/files-upload-error-schema-error.md) |

