# Workflows

```ts
const workflowsApi = new WorkflowsApi(client);
```

## Class Name

`WorkflowsApi`

## Methods

* [Workflows Step Completed](../../doc/controllers/workflows.md#workflows-step-completed)
* [Workflows Step Failed](../../doc/controllers/workflows.md#workflows-step-failed)
* [Workflows Update Step](../../doc/controllers/workflows.md#workflows-update-step)


# Workflows Step Completed

Indicate that an app's step in a workflow completed execution.

API method documentation: [https://api.slack.com/methods/workflows.stepCompleted](https://api.slack.com/methods/workflows.stepCompleted)

```ts
async workflowsStepCompleted(
  token: string,
  workflowStepExecuteId: string,
  outputs?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `workflow.steps:execute` |
| `workflowStepExecuteId` | `string` | Query, Required | Context identifier that maps to the correct workflow step execution. |
| `outputs` | `string \| undefined` | Query, Optional | Key-value object of outputs from your step. Keys of this object reflect the configured `key` properties of your [`outputs`](/reference/workflows/workflow_step#output) array from your `workflow_step` object. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`workflow.steps:execute`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const workflowStepExecuteId = 'workflow_step_execute_id2';

try {
  const response = await workflowsApi.workflowsStepCompleted(
    token,
    workflowStepExecuteId
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


# Workflows Step Failed

Indicate that an app's step in a workflow failed to execute.

API method documentation: [https://api.slack.com/methods/workflows.stepFailed](https://api.slack.com/methods/workflows.stepFailed)

```ts
async workflowsStepFailed(
  token: string,
  workflowStepExecuteId: string,
  error: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `workflow.steps:execute` |
| `workflowStepExecuteId` | `string` | Query, Required | Context identifier that maps to the correct workflow step execution. |
| `error` | `string` | Query, Required | A JSON-based object with a `message` property that should contain a human readable error message. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`workflow.steps:execute`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const workflowStepExecuteId = 'workflow_step_execute_id2';

const error = 'error4';

try {
  const response = await workflowsApi.workflowsStepFailed(
    token,
    workflowStepExecuteId,
    error
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


# Workflows Update Step

Update the configuration for a workflow extension step.

API method documentation: [https://api.slack.com/methods/workflows.updateStep](https://api.slack.com/methods/workflows.updateStep)

```ts
async workflowsUpdateStep(
  token: string,
  workflowStepEditId: string,
  inputs?: string,
  outputs?: string,
  stepName?: string,
  stepImageUrl?: string,
  requestOptions?: RequestOptions
): Promise<ApiResponse<DefaultSuccessTemplate>>
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `string` | Header, Required | Authentication token. Requires scope: `workflow.steps:execute` |
| `workflowStepEditId` | `string` | Query, Required | A context identifier provided with `view_submission` payloads used to call back to `workflows.updateStep`. |
| `inputs` | `string \| undefined` | Query, Optional | A JSON key-value map of inputs required from a user during configuration. This is the data your app expects to receive when the workflow step starts. **Please note**: the embedded variable format is set and replaced by the workflow system. You cannot create custom variables that will be replaced at runtime. [Read more about variables in workflow steps here](/workflows/steps#variables). |
| `outputs` | `string \| undefined` | Query, Optional | An JSON array of output objects used during step execution. This is the data your app agrees to provide when your workflow step was executed. |
| `stepName` | `string \| undefined` | Query, Optional | An optional field that can be used to override the step name that is shown in the Workflow Builder. |
| `stepImageUrl` | `string \| undefined` | Query, Optional | An optional field that can be used to override app image that is shown in the Workflow Builder. |
| `requestOptions` | `RequestOptions \| undefined` | Optional | Pass additional request options. |

## Requires scope

### slackAuth

`workflow.steps:execute`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `result` property of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```ts
const token = 'token6';

const workflowStepEditId = 'workflow_step_edit_id0';

try {
  const response = await workflowsApi.workflowsUpdateStep(
    token,
    workflowStepEditId
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

