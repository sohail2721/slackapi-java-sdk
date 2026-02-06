# Apps

```java
AppsController appsController = client.getAppsController();
```

## Class Name

`AppsController`


# Apps Uninstall

Uninstalls your app from a workspace.

API method documentation: [https://api.slack.com/methods/apps.uninstall](https://api.slack.com/methods/apps.uninstall)

```java
CompletableFuture<ApiResponse<AppsUninstallSchema>> appsUninstallAsync(
    final String token,
    final String clientId,
    final String clientSecret)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `none` |
| `clientId` | `String` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `String` | Query, Optional | Issued when you created your application. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AppsUninstallSchema`](../../doc/models/apps-uninstall-schema.md).

## Example Usage

```java
appsController.appsUninstallAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AppsUninstallErrorSchemaException) {
        AppsUninstallErrorSchemaException appsUninstallErrorSchemaException = (AppsUninstallErrorSchemaException) cause;
        appsUninstallErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AppsUninstallErrorSchemaException`](../../doc/models/apps-uninstall-error-schema-exception.md) |

