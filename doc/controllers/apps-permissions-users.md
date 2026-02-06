# Apps Permissions Users

```java
AppsPermissionsUsersController appsPermissionsUsersController = client.getAppsPermissionsUsersController();
```

## Class Name

`AppsPermissionsUsersController`

## Methods

* [Apps Permissions Users List](../../doc/controllers/apps-permissions-users.md#apps-permissions-users-list)
* [Apps Permissions Users Request](../../doc/controllers/apps-permissions-users.md#apps-permissions-users-request)


# Apps Permissions Users List

Returns list of user grants and corresponding scopes this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.users.list](https://api.slack.com/methods/apps.permissions.users.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> appsPermissionsUsersListAsync(
    final String token,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `none` |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

appsPermissionsUsersController.appsPermissionsUsersListAsync(token, null, null).thenAccept(result -> {
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


# Apps Permissions Users Request

Enables an app to trigger a permissions modal to grant an app access to a user access scope.

API method documentation: [https://api.slack.com/methods/apps.permissions.users.request](https://api.slack.com/methods/apps.permissions.users.request)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> appsPermissionsUsersRequestAsync(
    final String token,
    final String scopes,
    final String triggerId,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `none` |
| `scopes` | `String` | Query, Required | A comma separated list of user scopes to request for |
| `triggerId` | `String` | Query, Required | Token used to trigger the request |
| `user` | `String` | Query, Required | The user this scope is being requested for |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String scopes = "scopes4";
String triggerId = "trigger_id6";
String user = "user0";

appsPermissionsUsersController.appsPermissionsUsersRequestAsync(token, scopes, triggerId, user).thenAccept(result -> {
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
| Default | Standard failure response when trigger_id is invalid | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

