# Team

```ts
const teamApi = new TeamApi(client);
```

## Class Name

`TeamApi`

## Methods

* [Team Access Logs](../../doc/controllers/team.md#team-access-logs)
* [Team Billable Info](../../doc/controllers/team.md#team-billable-info)
* [Team Info](../../doc/controllers/team.md#team-info)
* [Team Integration Logs](../../doc/controllers/team.md#team-integration-logs)


# Team Access Logs

Gets the access logs for the current team.

API method documentation: [https://api.slack.com/methods/team.accessLogs](https://api.slack.com/methods/team.accessLogs)

```ts
async teamAccessLogs(
  token: string,
  before?: string,
  count?: string,
  page?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<TeamAccessLogsSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin` |
| `before` | `string \| undefined` | Query, Optional | End of time range of logs to include in results (inclusive). |
| `count` | `string \| undefined` | Query, Optional | - |
| `page` | `string \| undefined` | Query, Optional | - |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`TeamAccessLogsSchema`](../../doc/models/team-access-logs-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await teamApi.teamAccessLogs(token);

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
    if (error instanceof TeamAccessLogsErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | A workspace must be on a paid plan to use this method, otherwise the `paid_only` error is thrown: | [`TeamAccessLogsErrorSchemaError`](../../doc/models/team-access-logs-error-schema-error.md) |


# Team Billable Info

Gets billable users information for the current team.

API method documentation: [https://api.slack.com/methods/team.billableInfo](https://api.slack.com/methods/team.billableInfo)

```ts
async teamBillableInfo(
  token: string,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin` |
| `user` | `string \| undefined` | Query, Optional | A user to retrieve the billable information for. Defaults to all users. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await teamApi.teamBillableInfo(token);

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


# Team Info

Gets information about the current team.

API method documentation: [https://api.slack.com/methods/team.info](https://api.slack.com/methods/team.info)

```ts
async teamInfo(
  token: string,
  team?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<TeamInfoSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `team:read` |
| `team` | `string \| undefined` | Query, Optional | Team to get info on, if omitted, will return information about the current team. Will only return team that the authenticated token is allowed to see through external shared channels |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`team:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`TeamInfoSchema`](../../doc/models/team-info-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await teamApi.teamInfo(token);

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
    if (error instanceof TeamInfoErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamInfoErrorSchemaError`](../../doc/models/team-info-error-schema-error.md) |


# Team Integration Logs

Gets the integration logs for the current team.

API method documentation: [https://api.slack.com/methods/team.integrationLogs](https://api.slack.com/methods/team.integrationLogs)

```ts
async teamIntegrationLogs(
  token: string,
  appId?: string,
  changeType?: string,
  count?: string,
  page?: string,
  serviceId?: string,
  user?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<TeamIntegrationLogsSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `admin` |
| `appId` | `string \| undefined` | Query, Optional | Filter logs to this Slack app. Defaults to all logs. |
| `changeType` | `string \| undefined` | Query, Optional | Filter logs with this change type. Defaults to all logs. |
| `count` | `string \| undefined` | Query, Optional | - |
| `page` | `string \| undefined` | Query, Optional | - |
| `serviceId` | `string \| undefined` | Query, Optional | Filter logs to this service. Defaults to all logs. |
| `user` | `string \| undefined` | Query, Optional | Filter logs generated by this user’s actions. Defaults to all logs. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`TeamIntegrationLogsSchema`](../../doc/models/team-integration-logs-schema.md).

## Example Usage

```ts
const token = 'token6';

try {
  const response = await teamApi.teamIntegrationLogs(token);

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
    if (error instanceof TeamIntegrationLogsErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamIntegrationLogsErrorSchemaError`](../../doc/models/team-integration-logs-error-schema-error.md) |

