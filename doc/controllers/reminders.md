# Reminders

```java
RemindersController remindersController = client.getRemindersController();
```

## Class Name

`RemindersController`

## Methods

* [Reminders Add](../../doc/controllers/reminders.md#reminders-add)
* [Reminders Complete](../../doc/controllers/reminders.md#reminders-complete)
* [Reminders Delete](../../doc/controllers/reminders.md#reminders-delete)
* [Reminders Info](../../doc/controllers/reminders.md#reminders-info)
* [Reminders List](../../doc/controllers/reminders.md#reminders-list)


# Reminders Add

Creates a reminder.

API method documentation: [https://api.slack.com/methods/reminders.add](https://api.slack.com/methods/reminders.add)

```java
CompletableFuture<ApiResponse<RemindersAddSchema>> remindersAddAsync(
    final String token,
    final String text,
    final String time,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `reminders:write` |
| `text` | `String` | Form, Required | The content of the reminder |
| `time` | `String` | Form, Required | When this reminder should happen: the Unix timestamp (up to five years from now), the number of seconds until the reminder (if within 24 hours), or a natural language description (Ex. "in 15 minutes," or "every Thursday") |
| `user` | `String` | Form, Optional | The user who will receive the reminder. If no user is specified, the reminder will go to user who created it. |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RemindersAddSchema`](../../doc/models/reminders-add-schema.md).

## Example Usage

```java
String token = "token6";
String text = "text0";
String time = "time0";

remindersController.remindersAddAsync(token, text, time, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof RemindersAddErrorSchemaException) {
        RemindersAddErrorSchemaException remindersAddErrorSchemaException = (RemindersAddErrorSchemaException) cause;
        remindersAddErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`RemindersAddErrorSchemaException`](../../doc/models/reminders-add-error-schema-exception.md) |


# Reminders Complete

Marks a reminder as complete.

API method documentation: [https://api.slack.com/methods/reminders.complete](https://api.slack.com/methods/reminders.complete)

```java
CompletableFuture<ApiResponse<RemindersCompleteSchema>> remindersCompleteAsync(
    final String token,
    final String reminder)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `String` | Form, Optional | The ID of the reminder to be marked as complete |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RemindersCompleteSchema`](../../doc/models/reminders-complete-schema.md).

## Example Usage

```java
remindersController.remindersCompleteAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof RemindersCompleteErrorSchemaException) {
        RemindersCompleteErrorSchemaException remindersCompleteErrorSchemaException = (RemindersCompleteErrorSchemaException) cause;
        remindersCompleteErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`RemindersCompleteErrorSchemaException`](../../doc/models/reminders-complete-error-schema-exception.md) |


# Reminders Delete

Deletes a reminder.

API method documentation: [https://api.slack.com/methods/reminders.delete](https://api.slack.com/methods/reminders.delete)

```java
CompletableFuture<ApiResponse<RemindersDeleteSchema>> remindersDeleteAsync(
    final String token,
    final String reminder)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `reminders:write` |
| `reminder` | `String` | Form, Optional | The ID of the reminder |

## Requires scope

### slackAuth

`reminders:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RemindersDeleteSchema`](../../doc/models/reminders-delete-schema.md).

## Example Usage

```java
remindersController.remindersDeleteAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof RemindersDeleteErrorSchemaException) {
        RemindersDeleteErrorSchemaException remindersDeleteErrorSchemaException = (RemindersDeleteErrorSchemaException) cause;
        remindersDeleteErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`RemindersDeleteErrorSchemaException`](../../doc/models/reminders-delete-error-schema-exception.md) |


# Reminders Info

Gets information about a reminder.

API method documentation: [https://api.slack.com/methods/reminders.info](https://api.slack.com/methods/reminders.info)

```java
CompletableFuture<ApiResponse<RemindersInfoSchema>> remindersInfoAsync(
    final String token,
    final String reminder)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `reminders:read` |
| `reminder` | `String` | Query, Optional | The ID of the reminder |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RemindersInfoSchema`](../../doc/models/reminders-info-schema.md).

## Example Usage

```java
remindersController.remindersInfoAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof RemindersInfoErrorSchemaException) {
        RemindersInfoErrorSchemaException remindersInfoErrorSchemaException = (RemindersInfoErrorSchemaException) cause;
        remindersInfoErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`RemindersInfoErrorSchemaException`](../../doc/models/reminders-info-error-schema-exception.md) |


# Reminders List

Lists all reminders created by or for a given user.

API method documentation: [https://api.slack.com/methods/reminders.list](https://api.slack.com/methods/reminders.list)

```java
CompletableFuture<ApiResponse<RemindersListSchema>> remindersListAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `reminders:read` |

## Requires scope

### slackAuth

`reminders:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RemindersListSchema`](../../doc/models/reminders-list-schema.md).

## Example Usage

```java
remindersController.remindersListAsync(null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof RemindersListErrorSchemaException) {
        RemindersListErrorSchemaException remindersListErrorSchemaException = (RemindersListErrorSchemaException) cause;
        remindersListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`RemindersListErrorSchemaException`](../../doc/models/reminders-list-error-schema-exception.md) |

