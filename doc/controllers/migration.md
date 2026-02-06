# Migration

```ts
const migrationApi = new MigrationApi(client);
```

## Class Name

`MigrationApi`


# Migration Exchange

For Enterprise Grid workspaces, map local user IDs to global user IDs

API method documentation: [https://api.slack.com/methods/migration.exchange](https://api.slack.com/methods/migration.exchange)

```ts
async migrationExchange(
  token: string,
  users: string,
  teamId?: string,
  toOld?: boolean,
  requestOptions?: RequestOptions
): Promise<ApiResponse<MigrationExchangeSuccessSchema>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Query, Required | Authentication token. Requires scope: `tokens.basic` |
| `users` | `string` | Query, Required | A comma-separated list of user ids, up to 400 per request |
| `teamId` | `string \| undefined` | Query, Optional | Specify team_id starts with `T` in case of Org Token |
| `toOld` | `boolean \| undefined` | Query, Optional | Specify `true` to convert `W` global user IDs to workspace-specific `U` IDs. Defaults to `false`. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`tokens.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`MigrationExchangeSuccessSchema`](../../doc/models/migration-exchange-success-schema.md).

## Example Usage

```ts
const token = 'token6';

const users = 'users6';

try {
  const response = await migrationApi.migrationExchange(
    token,
    users
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
    if (error instanceof MigrationExchangeErrorSchemaError) {
      console.log(error.result);
    }
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response when there are no mappings to provide | [`MigrationExchangeErrorSchemaError`](../../doc/models/migration-exchange-error-schema-error.md) |

