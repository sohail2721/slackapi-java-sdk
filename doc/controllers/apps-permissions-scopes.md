# Apps Permissions Scopes

```java
AppsPermissionsScopesController appsPermissionsScopesController = client.getAppsPermissionsScopesController();
```

## Class Name

`AppsPermissionsScopesController`


# Apps Permissions Scopes List

Returns list of scopes this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.scopes.list](https://api.slack.com/methods/apps.permissions.scopes.list)

```java
CompletableFuture<ApiResponse<ApiPermissionsScopesListSuccessSchema>> appsPermissionsScopesListAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiPermissionsScopesListSuccessSchema`](../../doc/models/api-permissions-scopes-list-success-schema.md).

## Example Usage

```java
String token = "token6";

appsPermissionsScopesController.appsPermissionsScopesListAsync(token).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AppsPermissionsScopesListErrorSchemaException) {
        AppsPermissionsScopesListErrorSchemaException appsPermissionsScopesListErrorSchemaException = (AppsPermissionsScopesListErrorSchemaException) cause;
        appsPermissionsScopesListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AppsPermissionsScopesListErrorSchemaException`](../../doc/models/apps-permissions-scopes-list-error-schema-exception.md) |

