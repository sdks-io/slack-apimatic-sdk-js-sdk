# Admin Teams

```ts
const adminTeamsApi = new AdminTeamsApi(client);
```

## Class Name

`AdminTeamsApi`

## Methods

* [Admin Teams Create](../../doc/controllers/admin-teams.md#admin-teams-create)
* [Admin Teams List](../../doc/controllers/admin-teams.md#admin-teams-list)


# Admin Teams Create

Create an Enterprise team.

API method documentation: [https://api.slack.com/methods/admin.teams.create](https://api.slack.com/methods/admin.teams.create)

```ts
async adminTeamsCreate(
  token: string,
  teamDomain: string,
  teamName: string,
  teamDescription?: string,
  teamDiscoverability?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamDomain` | `string` | Form, Required | Team domain (for example, slacksoftballteam). |
| `teamName` | `string` | Form, Required | Team name (for example, Slack Softball Team). |
| `teamDescription` | `string \| undefined` | Form, Optional | Description for the team. |
| `teamDiscoverability` | `string \| undefined` | Form, Optional | Who can join the team. A team's discoverability can be `open`, `closed`, `invite_only`, or `unlisted`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const teamDomain = 'team_domain2';

const teamName = 'team_name6';

try {
  const response = await adminTeamsApi.adminTeamsCreate(
    token,
    teamDomain,
    teamName
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


# Admin Teams List

List all teams on an Enterprise organization

API method documentation: [https://api.slack.com/methods/admin.teams.list](https://api.slack.com/methods/admin.teams.list)

```ts
async adminTeamsList(
  token: string,
  limit?: number,
  cursor?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `admin.teams:read` |
| `limit` | `number \| undefined` | Query, Optional | The maximum number of items to return. Must be between 1 - 100 both inclusive. |
| `cursor` | `string \| undefined` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
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
  const response = await adminTeamsApi.adminTeamsList(token);

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

