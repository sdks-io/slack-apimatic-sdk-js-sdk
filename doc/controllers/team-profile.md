# Team Profile

```ts
const teamProfileApi = new TeamProfileApi(client);
```

## Class Name

`TeamProfileApi`


# Team Profile Get

Retrieve a team's profile.

API method documentation: [https://api.slack.com/methods/team.profile.get](https://api.slack.com/methods/team.profile.get)

```ts
async teamProfileGet(
  token: string,
  visibility?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<TeamProfileGetSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `users.profile:read` |
| `visibility` | `string \| undefined` | Query, Optional | Filter by visibility. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`users.profile:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`TeamProfileGetSuccessSchema`](../../doc/models/team-profile-get-success-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await teamProfileApi.teamProfileGet(token);

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
    if (error instanceof TeamProfileGetErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamProfileGetErrorSchemaError`](../../doc/models/team-profile-get-error-schema-error.md) |

