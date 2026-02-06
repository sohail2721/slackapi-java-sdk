# Apps Event Authorizations

```java
AppsEventAuthorizationsController appsEventAuthorizationsController = client.getAppsEventAuthorizationsController();
```

## Class Name

`AppsEventAuthorizationsController`


# Apps Event Authorizations List

Get a list of authorizations for the given event context. Each authorization represents an app installation that the event is visible to.

API method documentation: [https://api.slack.com/methods/apps.event.authorizations.list](https://api.slack.com/methods/apps.event.authorizations.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> appsEventAuthorizationsListAsync(
    final String token,
    final String eventContext,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `authorizations:read` |
| `eventContext` | `String` | Query, Required | - |
| `cursor` | `String` | Query, Optional | - |
| `limit` | `Integer` | Query, Optional | - |

## Requires scope

### slackAuth

`authorizations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String eventContext = "event_context0";

appsEventAuthorizationsController.appsEventAuthorizationsListAsync(token, eventContext, null, null).thenAccept(result -> {
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

