# Admin Users Session

```java
AdminUsersSessionController adminUsersSessionController = client.getAdminUsersSessionController();
```

## Class Name

`AdminUsersSessionController`

## Methods

* [Admin Users Session Invalidate](../../doc/controllers/admin-users-session.md#admin-users-session-invalidate)
* [Admin Users Session Reset](../../doc/controllers/admin-users-session.md#admin-users-session-reset)


# Admin Users Session Invalidate

Invalidate a single session for a user by session_id

API method documentation: [https://api.slack.com/methods/admin.users.session.invalidate](https://api.slack.com/methods/admin.users.session.invalidate)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersSessionInvalidateAsync(
    final String token,
    final String teamId,
    final int sessionId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | ID of the team that the session belongs to |
| `sessionId` | `int` | Form, Required | - |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
int sessionId = 2;

adminUsersSessionController.adminUsersSessionInvalidateAsync(token, teamId, sessionId).thenAccept(result -> {
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


# Admin Users Session Reset

Wipes all valid sessions on all devices for a given user

API method documentation: [https://api.slack.com/methods/admin.users.session.reset](https://api.slack.com/methods/admin.users.session.reset)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersSessionResetAsync(
    final String token,
    final String userId,
    final Boolean mobileOnly,
    final Boolean webOnly)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `userId` | `String` | Form, Required | The ID of the user to wipe sessions for |
| `mobileOnly` | `Boolean` | Form, Optional | Only expire mobile sessions (default: false) |
| `webOnly` | `Boolean` | Form, Optional | Only expire web sessions (default: false) |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String userId = "user_id8";

adminUsersSessionController.adminUsersSessionResetAsync(token, userId, null, null).thenAccept(result -> {
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

