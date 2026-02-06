# Team

```java
TeamController teamController = client.getTeamController();
```

## Class Name

`TeamController`

## Methods

* [Team Access Logs](../../doc/controllers/team.md#team-access-logs)
* [Team Billable Info](../../doc/controllers/team.md#team-billable-info)
* [Team Info](../../doc/controllers/team.md#team-info)
* [Team Integration Logs](../../doc/controllers/team.md#team-integration-logs)


# Team Access Logs

Gets the access logs for the current team.

API method documentation: [https://api.slack.com/methods/team.accessLogs](https://api.slack.com/methods/team.accessLogs)

```java
CompletableFuture<ApiResponse<TeamAccessLogsSchema>> teamAccessLogsAsync(
    final String token,
    final String before,
    final String count,
    final String page)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin` |
| `before` | `String` | Query, Optional | End of time range of logs to include in results (inclusive). |
| `count` | `String` | Query, Optional | - |
| `page` | `String` | Query, Optional | - |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`TeamAccessLogsSchema`](../../doc/models/team-access-logs-schema.md).

## Example Usage

```java
String token = "token6";

teamController.teamAccessLogsAsync(token, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof TeamAccessLogsErrorSchemaException) {
        TeamAccessLogsErrorSchemaException teamAccessLogsErrorSchemaException = (TeamAccessLogsErrorSchemaException) cause;
        teamAccessLogsErrorSchemaException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | A workspace must be on a paid plan to use this method, otherwise the `paid_only` error is thrown: | [`TeamAccessLogsErrorSchemaException`](../../doc/models/team-access-logs-error-schema-exception.md) |


# Team Billable Info

Gets billable users information for the current team.

API method documentation: [https://api.slack.com/methods/team.billableInfo](https://api.slack.com/methods/team.billableInfo)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> teamBillableInfoAsync(
    final String token,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin` |
| `user` | `String` | Query, Optional | A user to retrieve the billable information for. Defaults to all users. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

teamController.teamBillableInfoAsync(token, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof DefaultErrorTemplateException) {
        DefaultErrorTemplateException defaultErrorTemplateException = (DefaultErrorTemplateException) cause;
        defaultErrorTemplateException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Team Info

Gets information about the current team.

API method documentation: [https://api.slack.com/methods/team.info](https://api.slack.com/methods/team.info)

```java
CompletableFuture<ApiResponse<TeamInfoSchema>> teamInfoAsync(
    final String token,
    final String team)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `team:read` |
| `team` | `String` | Query, Optional | Team to get info on, if omitted, will return information about the current team. Will only return team that the authenticated token is allowed to see through external shared channels |

## Requires scope

### slackAuth

`team:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`TeamInfoSchema`](../../doc/models/team-info-schema.md).

## Example Usage

```java
String token = "token6";

teamController.teamInfoAsync(token, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof TeamInfoErrorSchemaException) {
        TeamInfoErrorSchemaException teamInfoErrorSchemaException = (TeamInfoErrorSchemaException) cause;
        teamInfoErrorSchemaException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamInfoErrorSchemaException`](../../doc/models/team-info-error-schema-exception.md) |


# Team Integration Logs

Gets the integration logs for the current team.

API method documentation: [https://api.slack.com/methods/team.integrationLogs](https://api.slack.com/methods/team.integrationLogs)

```java
CompletableFuture<ApiResponse<TeamIntegrationLogsSchema>> teamIntegrationLogsAsync(
    final String token,
    final String appId,
    final String changeType,
    final String count,
    final String page,
    final String serviceId,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin` |
| `appId` | `String` | Query, Optional | Filter logs to this Slack app. Defaults to all logs. |
| `changeType` | `String` | Query, Optional | Filter logs with this change type. Defaults to all logs. |
| `count` | `String` | Query, Optional | - |
| `page` | `String` | Query, Optional | - |
| `serviceId` | `String` | Query, Optional | Filter logs to this service. Defaults to all logs. |
| `user` | `String` | Query, Optional | Filter logs generated by this user’s actions. Defaults to all logs. |

## Requires scope

### slackAuth

`admin`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`TeamIntegrationLogsSchema`](../../doc/models/team-integration-logs-schema.md).

## Example Usage

```java
String token = "token6";

teamController.teamIntegrationLogsAsync(token, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof TeamIntegrationLogsErrorSchemaException) {
        TeamIntegrationLogsErrorSchemaException teamIntegrationLogsErrorSchemaException = (TeamIntegrationLogsErrorSchemaException) cause;
        teamIntegrationLogsErrorSchemaException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`TeamIntegrationLogsErrorSchemaException`](../../doc/models/team-integration-logs-error-schema-exception.md) |

