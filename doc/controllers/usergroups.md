# Usergroups

```java
UsergroupsController usergroupsController = client.getUsergroupsController();
```

## Class Name

`UsergroupsController`

## Methods

* [Usergroups Create](../../doc/controllers/usergroups.md#usergroups-create)
* [Usergroups Disable](../../doc/controllers/usergroups.md#usergroups-disable)
* [Usergroups Enable](../../doc/controllers/usergroups.md#usergroups-enable)
* [Usergroups List](../../doc/controllers/usergroups.md#usergroups-list)
* [Usergroups Update](../../doc/controllers/usergroups.md#usergroups-update)


# Usergroups Create

Create a User Group

API method documentation: [https://api.slack.com/methods/usergroups.create](https://api.slack.com/methods/usergroups.create)

```java
CompletableFuture<ApiResponse<UsergroupsCreateSchema>> usergroupsCreateAsync(
    final String token,
    final String name,
    final String channels,
    final String description,
    final String handle,
    final Boolean includeCount)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `name` | `String` | Form, Required | A name for the User Group. Must be unique among User Groups. |
| `channels` | `String` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `description` | `String` | Form, Optional | A short description of the User Group. |
| `handle` | `String` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `includeCount` | `Boolean` | Form, Optional | Include the number of users in each User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsergroupsCreateSchema`](../../doc/models/usergroups-create-schema.md).

## Example Usage

```java
String token = "token6";
String name = "name0";

usergroupsController.usergroupsCreateAsync(token, name, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsergroupsCreateErrorSchemaException) {
        UsergroupsCreateErrorSchemaException usergroupsCreateErrorSchemaException = (UsergroupsCreateErrorSchemaException) cause;
        usergroupsCreateErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsergroupsCreateErrorSchemaException`](../../doc/models/usergroups-create-error-schema-exception.md) |


# Usergroups Disable

Disable an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.disable](https://api.slack.com/methods/usergroups.disable)

```java
CompletableFuture<ApiResponse<UsergroupsDisableSchema>> usergroupsDisableAsync(
    final String token,
    final String usergroup,
    final Boolean includeCount)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `String` | Form, Required | The encoded ID of the User Group to disable. |
| `includeCount` | `Boolean` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsergroupsDisableSchema`](../../doc/models/usergroups-disable-schema.md).

## Example Usage

```java
String token = "token6";
String usergroup = "usergroup2";

usergroupsController.usergroupsDisableAsync(token, usergroup, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsergroupsDisableErrorSchemaException) {
        UsergroupsDisableErrorSchemaException usergroupsDisableErrorSchemaException = (UsergroupsDisableErrorSchemaException) cause;
        usergroupsDisableErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsergroupsDisableErrorSchemaException`](../../doc/models/usergroups-disable-error-schema-exception.md) |


# Usergroups Enable

Enable a User Group

API method documentation: [https://api.slack.com/methods/usergroups.enable](https://api.slack.com/methods/usergroups.enable)

```java
CompletableFuture<ApiResponse<UsergroupsEnableSchema>> usergroupsEnableAsync(
    final String token,
    final String usergroup,
    final Boolean includeCount)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `String` | Form, Required | The encoded ID of the User Group to enable. |
| `includeCount` | `Boolean` | Form, Optional | Include the number of users in the User Group. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsergroupsEnableSchema`](../../doc/models/usergroups-enable-schema.md).

## Example Usage

```java
String token = "token6";
String usergroup = "usergroup2";

usergroupsController.usergroupsEnableAsync(token, usergroup, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsergroupsEnableErrorSchemaException) {
        UsergroupsEnableErrorSchemaException usergroupsEnableErrorSchemaException = (UsergroupsEnableErrorSchemaException) cause;
        usergroupsEnableErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsergroupsEnableErrorSchemaException`](../../doc/models/usergroups-enable-error-schema-exception.md) |


# Usergroups List

List all User Groups for a team

API method documentation: [https://api.slack.com/methods/usergroups.list](https://api.slack.com/methods/usergroups.list)

```java
CompletableFuture<ApiResponse<UsergroupsListSchema>> usergroupsListAsync(
    final String token,
    final Boolean includeUsers,
    final Boolean includeCount,
    final Boolean includeDisabled)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `usergroups:read` |
| `includeUsers` | `Boolean` | Query, Optional | Include the list of users for each User Group. |
| `includeCount` | `Boolean` | Query, Optional | Include the number of users in each User Group. |
| `includeDisabled` | `Boolean` | Query, Optional | Include disabled User Groups. |

## Requires scope

### slackAuth

`usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsergroupsListSchema`](../../doc/models/usergroups-list-schema.md).

## Example Usage

```java
String token = "token6";

usergroupsController.usergroupsListAsync(token, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsergroupsListErrorSchemaException) {
        UsergroupsListErrorSchemaException usergroupsListErrorSchemaException = (UsergroupsListErrorSchemaException) cause;
        usergroupsListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsergroupsListErrorSchemaException`](../../doc/models/usergroups-list-error-schema-exception.md) |


# Usergroups Update

Update an existing User Group

API method documentation: [https://api.slack.com/methods/usergroups.update](https://api.slack.com/methods/usergroups.update)

```java
CompletableFuture<ApiResponse<UsergroupsUpdateSchema>> usergroupsUpdateAsync(
    final String token,
    final String usergroup,
    final String handle,
    final String description,
    final String channels,
    final Boolean includeCount,
    final String name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `usergroups:write` |
| `usergroup` | `String` | Form, Required | The encoded ID of the User Group to update. |
| `handle` | `String` | Form, Optional | A mention handle. Must be unique among channels, users and User Groups. |
| `description` | `String` | Form, Optional | A short description of the User Group. |
| `channels` | `String` | Form, Optional | A comma separated string of encoded channel IDs for which the User Group uses as a default. |
| `includeCount` | `Boolean` | Form, Optional | Include the number of users in the User Group. |
| `name` | `String` | Form, Optional | A name for the User Group. Must be unique among User Groups. |

## Requires scope

### slackAuth

`usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsergroupsUpdateSchema`](../../doc/models/usergroups-update-schema.md).

## Example Usage

```java
String token = "token6";
String usergroup = "usergroup2";

usergroupsController.usergroupsUpdateAsync(token, usergroup, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsergroupsUpdateErrorSchemaException) {
        UsergroupsUpdateErrorSchemaException usergroupsUpdateErrorSchemaException = (UsergroupsUpdateErrorSchemaException) cause;
        usergroupsUpdateErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsergroupsUpdateErrorSchemaException`](../../doc/models/usergroups-update-error-schema-exception.md) |

