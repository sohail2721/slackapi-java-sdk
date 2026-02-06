# Apps Permissions

```java
AppsPermissionsController appsPermissionsController = client.getAppsPermissionsController();
```

## Class Name

`AppsPermissionsController`

## Methods

* [Apps Permissions Info](../../doc/controllers/apps-permissions.md#apps-permissions-info)
* [Apps Permissions Request](../../doc/controllers/apps-permissions.md#apps-permissions-request)


# Apps Permissions Info

Returns list of permissions this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.info](https://api.slack.com/methods/apps.permissions.info)

```java
CompletableFuture<ApiResponse<AppsPermissionsInfoSchema>> appsPermissionsInfoAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AppsPermissionsInfoSchema`](../../doc/models/apps-permissions-info-schema.md).

## Example Usage

```java
appsPermissionsController.appsPermissionsInfoAsync(null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AppsPermissionsInfoErrorSchemaException) {
        AppsPermissionsInfoErrorSchemaException appsPermissionsInfoErrorSchemaException = (AppsPermissionsInfoErrorSchemaException) cause;
        appsPermissionsInfoErrorSchemaException.printStackTrace();
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
| Default | Standard failure response when used with an invalid token | [`AppsPermissionsInfoErrorSchemaException`](../../doc/models/apps-permissions-info-error-schema-exception.md) |


# Apps Permissions Request

Allows an app to request additional scopes

API method documentation: [https://api.slack.com/methods/apps.permissions.request](https://api.slack.com/methods/apps.permissions.request)

```java
CompletableFuture<ApiResponse<AppsPermissionsRequestSchema>> appsPermissionsRequestAsync(
    final String token,
    final String scopes,
    final String triggerId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `none` |
| `scopes` | `String` | Query, Required | A comma separated list of scopes to request for |
| `triggerId` | `String` | Query, Required | Token used to trigger the permissions API |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AppsPermissionsRequestSchema`](../../doc/models/apps-permissions-request-schema.md).

## Example Usage

```java
String token = "token6";
String scopes = "scopes4";
String triggerId = "trigger_id6";

appsPermissionsController.appsPermissionsRequestAsync(token, scopes, triggerId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AppsPermissionsRequestErrorSchemaException) {
        AppsPermissionsRequestErrorSchemaException appsPermissionsRequestErrorSchemaException = (AppsPermissionsRequestErrorSchemaException) cause;
        appsPermissionsRequestErrorSchemaException.printStackTrace();
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
| Default | Standard failure response when trigger_id is invalid | [`AppsPermissionsRequestErrorSchemaException`](../../doc/models/apps-permissions-request-error-schema-exception.md) |

