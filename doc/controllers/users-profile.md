# Users Profile

```java
UsersProfileController usersProfileController = client.getUsersProfileController();
```

## Class Name

`UsersProfileController`

## Methods

* [Users Profile Get](../../doc/controllers/users-profile.md#users-profile-get)
* [Users Profile Set](../../doc/controllers/users-profile.md#users-profile-set)


# Users Profile Get

Retrieves a user's profile information.

API method documentation: [https://api.slack.com/methods/users.profile.get](https://api.slack.com/methods/users.profile.get)

```java
CompletableFuture<ApiResponse<UsersProfileGetSchema>> usersProfileGetAsync(
    final String token,
    final Boolean includeLabels,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `users.profile:read` |
| `includeLabels` | `Boolean` | Query, Optional | Include labels for each ID in custom profile fields |
| `user` | `String` | Query, Optional | User to retrieve profile info for |

## Requires scope

### slackAuth

`users.profile:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersProfileGetSchema`](../../doc/models/users-profile-get-schema.md).

## Example Usage

```java
String token = "token6";

usersProfileController.usersProfileGetAsync(token, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersProfileGetErrorSchemaException) {
        UsersProfileGetErrorSchemaException usersProfileGetErrorSchemaException = (UsersProfileGetErrorSchemaException) cause;
        usersProfileGetErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersProfileGetErrorSchemaException`](../../doc/models/users-profile-get-error-schema-exception.md) |


# Users Profile Set

Set the profile information for a user.

API method documentation: [https://api.slack.com/methods/users.profile.set](https://api.slack.com/methods/users.profile.set)

```java
CompletableFuture<ApiResponse<UsersProfileSetSchema>> usersProfileSetAsync(
    final String token,
    final String name,
    final String profile,
    final String user,
    final String value)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `users.profile:write` |
| `name` | `String` | Form, Optional | Name of a single key to set. Usable only if `profile` is not passed. |
| `profile` | `String` | Form, Optional | Collection of key:value pairs presented as a URL-encoded JSON hash. At most 50 fields may be set. Each field name is limited to 255 characters. |
| `user` | `String` | Form, Optional | ID of user to change. This argument may only be specified by team admins on paid teams. |
| `value` | `String` | Form, Optional | Value to set a single key to. Usable only if `profile` is not passed. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersProfileSetSchema`](../../doc/models/users-profile-set-schema.md).

## Example Usage

```java
String token = "token6";

usersProfileController.usersProfileSetAsync(token, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersProfileSetErrorSchemaException) {
        UsersProfileSetErrorSchemaException usersProfileSetErrorSchemaException = (UsersProfileSetErrorSchemaException) cause;
        usersProfileSetErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersProfileSetErrorSchemaException`](../../doc/models/users-profile-set-error-schema-exception.md) |

