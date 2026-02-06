# Admin Apps Restricted

```java
AdminAppsRestrictedController adminAppsRestrictedController = client.getAdminAppsRestrictedController();
```

## Class Name

`AdminAppsRestrictedController`


# Admin Apps Restricted List

List restricted apps for an org or workspace.

API method documentation: [https://api.slack.com/methods/admin.apps.restricted.list](https://api.slack.com/methods/admin.apps.restricted.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminAppsRestrictedListAsync(
    final String token,
    final Integer limit,
    final String cursor,
    final String teamId,
    final String enterpriseId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin.apps:read` |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `teamId` | `String` | Query, Optional | - |
| `enterpriseId` | `String` | Query, Optional | - |

## Requires scope

### slackAuth

`admin.apps:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

adminAppsRestrictedController.adminAppsRestrictedListAsync(token, null, null, null, null).thenAccept(result -> {
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

