# Admin Apps

```java
AdminAppsController adminAppsController = client.getAdminAppsController();
```

## Class Name

`AdminAppsController`

## Methods

* [Admin Apps Approve](../../doc/controllers/admin-apps.md#admin-apps-approve)
* [Admin Apps Restrict](../../doc/controllers/admin-apps.md#admin-apps-restrict)


# Admin Apps Approve

Approve an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.approve](https://api.slack.com/methods/admin.apps.approve)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminAppsApproveAsync(
    final String token,
    final String appId,
    final String requestId,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `appId` | `String` | Form, Optional | The id of the app to approve. |
| `requestId` | `String` | Form, Optional | The id of the request to approve. |
| `teamId` | `String` | Form, Optional | - |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

adminAppsController.adminAppsApproveAsync(token, null, null, null).thenAccept(result -> {
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


# Admin Apps Restrict

Restrict an app for installation on a workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.restrict](https://api.slack.com/methods/admin.apps.restrict)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminAppsRestrictAsync(
    final String token,
    final String appId,
    final String requestId,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.apps:write` |
| `appId` | `String` | Form, Optional | The id of the app to restrict. |
| `requestId` | `String` | Form, Optional | The id of the request to restrict. |
| `teamId` | `String` | Form, Optional | - |

## Requires scope

### slackAuth

`admin.apps:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

adminAppsController.adminAppsRestrictAsync(token, null, null, null).thenAccept(result -> {
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

