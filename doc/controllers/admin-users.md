# Admin Users

```java
AdminUsersController adminUsersController = client.getAdminUsersController();
```

## Class Name

`AdminUsersController`

## Methods

* [Admin Users Assign](../../doc/controllers/admin-users.md#admin-users-assign)
* [Admin Users Invite](../../doc/controllers/admin-users.md#admin-users-invite)
* [Admin Users List](../../doc/controllers/admin-users.md#admin-users-list)
* [Admin Users Remove](../../doc/controllers/admin-users.md#admin-users-remove)
* [Admin Users Set Admin](../../doc/controllers/admin-users.md#admin-users-set-admin)
* [Admin Users Set Expiration](../../doc/controllers/admin-users.md#admin-users-set-expiration)
* [Admin Users Set Owner](../../doc/controllers/admin-users.md#admin-users-set-owner)
* [Admin Users Set Regular](../../doc/controllers/admin-users.md#admin-users-set-regular)


# Admin Users Assign

Add an Enterprise user to a workspace.

API method documentation: [https://api.slack.com/methods/admin.users.assign](https://api.slack.com/methods/admin.users.assign)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersAssignAsync(
    final String token,
    final String teamId,
    final String userId,
    final Boolean isRestricted,
    final Boolean isUltraRestricted,
    final String channelIds)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `String` | Form, Required | The ID of the user to add to the workspace. |
| `isRestricted` | `Boolean` | Form, Optional | True if user should be added to the workspace as a guest. |
| `isUltraRestricted` | `Boolean` | Form, Optional | True if user should be added to the workspace as a single-channel guest. |
| `channelIds` | `String` | Form, Optional | Comma separated values of channel IDs to add user in the new workspace. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String userId = "user_id8";

adminUsersController.adminUsersAssignAsync(token, teamId, userId, null, null, null).thenAccept(result -> {
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


# Admin Users Invite

Invite a user to a workspace.

API method documentation: [https://api.slack.com/methods/admin.users.invite](https://api.slack.com/methods/admin.users.invite)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersInviteAsync(
    final String token,
    final String teamId,
    final String email,
    final String channelIds,
    final String customMessage,
    final String realName,
    final Boolean resend,
    final Boolean isRestricted,
    final Boolean isUltraRestricted,
    final String guestExpirationTs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | The ID (`T1234`) of the workspace. |
| `email` | `String` | Form, Required | The email address of the person to invite. |
| `channelIds` | `String` | Form, Required | A comma-separated list of `channel_id`s for this user to join. At least one channel is required. |
| `customMessage` | `String` | Form, Optional | An optional message to send to the user in the invite email. |
| `realName` | `String` | Form, Optional | Full name of the user. |
| `resend` | `Boolean` | Form, Optional | Allow this invite to be resent in the future if a user has not signed up yet. (default: false) |
| `isRestricted` | `Boolean` | Form, Optional | Is this user a multi-channel guest user? (default: false) |
| `isUltraRestricted` | `Boolean` | Form, Optional | Is this user a single channel guest user? (default: false) |
| `guestExpirationTs` | `String` | Form, Optional | Timestamp when guest account should be disabled. Only include this timestamp if you are inviting a guest user and you want their account to expire on a certain date. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String email = "email6";
String channelIds = "channel_ids8";

adminUsersController.adminUsersInviteAsync(token, teamId, email, channelIds, null, null, null, null, null, null).thenAccept(result -> {
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


# Admin Users List

List users on a workspace

API method documentation: [https://api.slack.com/methods/admin.users.list](https://api.slack.com/methods/admin.users.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersListAsync(
    final String token,
    final String teamId,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:read` |
| `teamId` | `String` | Query, Required | The ID (`T1234`) of the workspace. |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
| `limit` | `Integer` | Query, Optional | Limit for how many users to be retrieved per page |

## Requires scope

### slackAuth

`admin.users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";

adminUsersController.adminUsersListAsync(token, teamId, null, null).thenAccept(result -> {
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


# Admin Users Remove

Remove a user from a workspace.

API method documentation: [https://api.slack.com/methods/admin.users.remove](https://api.slack.com/methods/admin.users.remove)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersRemoveAsync(
    final String token,
    final String teamId,
    final String userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `String` | Form, Required | The ID of the user to remove. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String userId = "user_id8";

adminUsersController.adminUsersRemoveAsync(token, teamId, userId).thenAccept(result -> {
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


# Admin Users Set Admin

Set an existing guest, regular user, or owner to be an admin user.

API method documentation: [https://api.slack.com/methods/admin.users.setAdmin](https://api.slack.com/methods/admin.users.setAdmin)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersSetAdminAsync(
    final String token,
    final String teamId,
    final String userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `String` | Form, Required | The ID of the user to designate as an admin. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String userId = "user_id8";

adminUsersController.adminUsersSetAdminAsync(token, teamId, userId).thenAccept(result -> {
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


# Admin Users Set Expiration

Set an expiration for a guest user

API method documentation: [https://api.slack.com/methods/admin.users.setExpiration](https://api.slack.com/methods/admin.users.setExpiration)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersSetExpirationAsync(
    final String token,
    final String teamId,
    final String userId,
    final int expirationTs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `String` | Form, Required | The ID of the user to set an expiration for. |
| `expirationTs` | `int` | Form, Required | Timestamp when guest account should be disabled. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String userId = "user_id8";
int expirationTs = 186;

adminUsersController.adminUsersSetExpirationAsync(token, teamId, userId, expirationTs).thenAccept(result -> {
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


# Admin Users Set Owner

Set an existing guest, regular user, or admin user to be a workspace owner.

API method documentation: [https://api.slack.com/methods/admin.users.setOwner](https://api.slack.com/methods/admin.users.setOwner)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersSetOwnerAsync(
    final String token,
    final String teamId,
    final String userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `String` | Form, Required | Id of the user to promote to owner. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String userId = "user_id8";

adminUsersController.adminUsersSetOwnerAsync(token, teamId, userId).thenAccept(result -> {
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


# Admin Users Set Regular

Set an existing guest user, admin user, or owner to be a regular user.

API method documentation: [https://api.slack.com/methods/admin.users.setRegular](https://api.slack.com/methods/admin.users.setRegular)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsersSetRegularAsync(
    final String token,
    final String teamId,
    final String userId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.users:write` |
| `teamId` | `String` | Form, Required | The ID (`T1234`) of the workspace. |
| `userId` | `String` | Form, Required | The ID of the user to designate as a regular user. |

## Requires scope

### slackAuth

`admin.users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String userId = "user_id8";

adminUsersController.adminUsersSetRegularAsync(token, teamId, userId).thenAccept(result -> {
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

