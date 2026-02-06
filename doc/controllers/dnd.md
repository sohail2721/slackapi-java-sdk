# Dnd

```java
DndController dndController = client.getDndController();
```

## Class Name

`DndController`

## Methods

* [Dnd End Dnd](../../doc/controllers/dnd.md#dnd-end-dnd)
* [Dnd End Snooze](../../doc/controllers/dnd.md#dnd-end-snooze)
* [Dnd Info](../../doc/controllers/dnd.md#dnd-info)
* [Dnd Set Snooze](../../doc/controllers/dnd.md#dnd-set-snooze)
* [Dnd Team Info](../../doc/controllers/dnd.md#dnd-team-info)


# Dnd End Dnd

Ends the current user's Do Not Disturb session immediately.

API method documentation: [https://api.slack.com/methods/dnd.endDnd](https://api.slack.com/methods/dnd.endDnd)

```java
CompletableFuture<ApiResponse<DndEndDndSchema>> dndEndDndAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `dnd:write` |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DndEndDndSchema`](../../doc/models/dnd-end-dnd-schema.md).

## Example Usage

```java
String token = "token6";

dndController.dndEndDndAsync(token).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof DndEndDndErrorSchemaException) {
        DndEndDndErrorSchemaException dndEndDndErrorSchemaException = (DndEndDndErrorSchemaException) cause;
        dndEndDndErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`DndEndDndErrorSchemaException`](../../doc/models/dnd-end-dnd-error-schema-exception.md) |


# Dnd End Snooze

Ends the current user's snooze mode immediately.

API method documentation: [https://api.slack.com/methods/dnd.endSnooze](https://api.slack.com/methods/dnd.endSnooze)

```java
CompletableFuture<ApiResponse<DndEndSnoozeSchema>> dndEndSnoozeAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `dnd:write` |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DndEndSnoozeSchema`](../../doc/models/dnd-end-snooze-schema.md).

## Example Usage

```java
String token = "token6";

dndController.dndEndSnoozeAsync(token).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof DndEndSnoozeErrorSchemaException) {
        DndEndSnoozeErrorSchemaException dndEndSnoozeErrorSchemaException = (DndEndSnoozeErrorSchemaException) cause;
        dndEndSnoozeErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`DndEndSnoozeErrorSchemaException`](../../doc/models/dnd-end-snooze-error-schema-exception.md) |


# Dnd Info

Retrieves a user's current Do Not Disturb status.

API method documentation: [https://api.slack.com/methods/dnd.info](https://api.slack.com/methods/dnd.info)

```java
CompletableFuture<ApiResponse<DndInfoSchema>> dndInfoAsync(
    final String token,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `dnd:read` |
| `user` | `String` | Query, Optional | User to fetch status for (defaults to current user) |

## Requires scope

### slackAuth

`dnd:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DndInfoSchema`](../../doc/models/dnd-info-schema.md).

## Example Usage

```java
dndController.dndInfoAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof DndInfoErrorSchemaException) {
        DndInfoErrorSchemaException dndInfoErrorSchemaException = (DndInfoErrorSchemaException) cause;
        dndInfoErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`DndInfoErrorSchemaException`](../../doc/models/dnd-info-error-schema-exception.md) |


# Dnd Set Snooze

Turns on Do Not Disturb mode for the current user, or changes its duration.

API method documentation: [https://api.slack.com/methods/dnd.setSnooze](https://api.slack.com/methods/dnd.setSnooze)

```java
CompletableFuture<ApiResponse<DndSetSnoozeSchema>> dndSetSnoozeAsync(
    final String token,
    final String numMinutes)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `dnd:write` |
| `numMinutes` | `String` | Form, Required | Number of minutes, from now, to snooze until. |

## Requires scope

### slackAuth

`dnd:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DndSetSnoozeSchema`](../../doc/models/dnd-set-snooze-schema.md).

## Example Usage

```java
String token = "token6";
String numMinutes = "num_minutes0";

dndController.dndSetSnoozeAsync(token, numMinutes).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof DndSetSnoozeErrorSchemaException) {
        DndSetSnoozeErrorSchemaException dndSetSnoozeErrorSchemaException = (DndSetSnoozeErrorSchemaException) cause;
        dndSetSnoozeErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`DndSetSnoozeErrorSchemaException`](../../doc/models/dnd-set-snooze-error-schema-exception.md) |


# Dnd Team Info

Retrieves the Do Not Disturb status for up to 50 users on a team.

API method documentation: [https://api.slack.com/methods/dnd.teamInfo](https://api.slack.com/methods/dnd.teamInfo)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> dndTeamInfoAsync(
    final String token,
    final String users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `dnd:read` |
| `users` | `String` | Query, Optional | Comma-separated list of users to fetch Do Not Disturb status for |

## Requires scope

### slackAuth

`dnd:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
dndController.dndTeamInfoAsync(null, null).thenAccept(result -> {
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

