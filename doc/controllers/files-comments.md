# Files Comments

```ts
const filesCommentsApi = new FilesCommentsApi(client);
```

## Class Name

`FilesCommentsApi`


# Files Comments Delete

Deletes an existing comment on a file.

API method documentation: [https://api.slack.com/methods/files.comments.delete](https://api.slack.com/methods/files.comments.delete)

```ts
async filesCommentsDelete(
  token?: string,
  file?: string,
  id?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<FilesCommentsDeleteSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string \| undefined` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `string \| undefined` | Form, Optional | File to delete a comment from. |
| `id` | `string \| undefined` | Form, Optional | The comment to delete. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`FilesCommentsDeleteSchema`](../../doc/models/files-comments-delete-schema.md).

## Example Usage

```ts
try {
  const response = await filesCommentsApi.filesCommentsDelete();

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
    if (error instanceof FilesCommentsDeleteErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Standard failure response when used with an invalid token | [`FilesCommentsDeleteErrorSchemaError`](../../doc/models/files-comments-delete-error-schema-error.md) |

