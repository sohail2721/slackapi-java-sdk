# Usergroups Users

```java
UsergroupsUsersController usergroupsUsersController = client.getUsergroupsUsersController();
```

## Class Name

`UsergroupsUsersController`

## Methods

* [Usergroups Users List](../../doc/controllers/usergroups-users.md#usergroups-users-list)
* [Usergroups Users Update](../../doc/controllers/usergroups-users.md#usergroups-users-update)


# Usergroups Users List

List all users in a User Group

API method documentation: [https://api.slack.com/methods/usergroups.users.list](https://api.slack.com/methods/usergroups.users.list)

```java
CompletableFuture<ApiResponse<UsergroupsUsersListSchema>> usergroupsUsersListAsync(
    final String token,
    final String usergroup,
    final Boolean includeDisabled)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `usergroups:read` |
| `usergroup` | `String` | Query, Required | The encoded ID of the User Group to update. |
| `includeDisabled` | `Boolean` | Query, Optional | Allow results that involve disabled User Groups. |

## Requires scope

### slackAuth

`usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsergroupsUsersListSchema`](../../doc/models/usergroups-users-list-schema.md).

## Example Usage

```java
String token = "token6";
String usergroup = "usergroup2";

usergroupsUsersController.usergroupsUsersListAsync(token, usergroup, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsergroupsUsersListErrorSchemaException) {
        UsergroupsUsersListErrorSchemaException usergroupsUsersListErrorSchemaException = (UsergroupsUsersListErrorSchemaException) cause;
        usergroupsUsersListErrorSchemaException.printStackTrace();
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
| Default | Standard failure response when used with an invalid token | [`UsergroupsUsersListErrorSchemaException`](../../doc/models/usergroups-users-list-error-schema-exception.md) |


# Usergroups Users Update

Update the list of users for a User Group

API method documentation: [https://api.slack.com/methods/usergroups.users.update](https://api.slack.com/methods/usergroups.users.update)

```java
CompletableFuture<ApiResponse<UsergroupsUsersUpdateSchema>> usergroupsUsersUpdateAsync(
    final String token,
    final String usergroup,
    final String users,
    final Boolean includeCount)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `String` | Form, Required | The encoded ID of the User Group to update. |
| `users` | `String` | Form, Required | A comma separated string of encoded user IDs that represent the entire list of users for the User Group. |
| `includeCount` | `Boolean` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsergroupsUsersUpdateSchema`](../../doc/models/usergroups-users-update-schema.md).

## Example Usage

```java
String token = "token6";
String usergroup = "usergroup2";
String users = "users6";

usergroupsUsersController.usergroupsUsersUpdateAsync(token, usergroup, users, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsergroupsUsersUpdateErrorSchemaException) {
        UsergroupsUsersUpdateErrorSchemaException usergroupsUsersUpdateErrorSchemaException = (UsergroupsUsersUpdateErrorSchemaException) cause;
        usergroupsUsersUpdateErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsergroupsUsersUpdateErrorSchemaException`](../../doc/models/usergroups-users-update-error-schema-exception.md) |

