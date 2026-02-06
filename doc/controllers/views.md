# Views

```java
ViewsController viewsController = client.getViewsController();
```

## Class Name

`ViewsController`

## Methods

* [Views Open](../../doc/controllers/views.md#views-open)
* [Views Publish](../../doc/controllers/views.md#views-publish)
* [Views Push](../../doc/controllers/views.md#views-push)
* [Views Update](../../doc/controllers/views.md#views-update)


# Views Open

Open a view for a user.

API method documentation: [https://api.slack.com/methods/views.open](https://api.slack.com/methods/views.open)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> viewsOpenAsync(
    final String token,
    final String triggerId,
    final String view)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `none` |
| `triggerId` | `String` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `String` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String triggerId = "trigger_id6";
String view = "view2";

viewsController.viewsOpenAsync(token, triggerId, view).thenAccept(result -> {
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
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Publish

Publish a static view for a User.

API method documentation: [https://api.slack.com/methods/views.publish](https://api.slack.com/methods/views.publish)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> viewsPublishAsync(
    final String token,
    final String userId,
    final String view,
    final String hash)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `none` |
| `userId` | `String` | Query, Required | `id` of the user you want publish a view to. |
| `view` | `String` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `String` | Query, Optional | A string that represents view state to protect against possible race conditions. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String userId = "user_id8";
String view = "view2";

viewsController.viewsPublishAsync(token, userId, view, null).thenAccept(result -> {
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
| Default | Typical error response, before getting to any possible validation errors. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Push

Push a view onto the stack of a root view.

API method documentation: [https://api.slack.com/methods/views.push](https://api.slack.com/methods/views.push)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> viewsPushAsync(
    final String token,
    final String triggerId,
    final String view)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `none` |
| `triggerId` | `String` | Query, Required | Exchange a trigger to post to the user. |
| `view` | `String` | Query, Required | A [view payload](/reference/surfaces/views). This must be a JSON-encoded string. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String triggerId = "trigger_id6";
String view = "view2";

viewsController.viewsPushAsync(token, triggerId, view).thenAccept(result -> {
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
| Default | Typical error response. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Views Update

Update an existing view.

API method documentation: [https://api.slack.com/methods/views.update](https://api.slack.com/methods/views.update)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> viewsUpdateAsync(
    final String token,
    final String viewId,
    final String externalId,
    final String view,
    final String hash)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `none` |
| `viewId` | `String` | Query, Optional | A unique identifier of the view to be updated. Either `view_id` or `external_id` is required. |
| `externalId` | `String` | Query, Optional | A unique identifier of the view set by the developer. Must be unique for all views on a team. Max length of 255 characters. Either `view_id` or `external_id` is required. |
| `view` | `String` | Query, Optional | A [view object](/reference/surfaces/views). This must be a JSON-encoded string. |
| `hash` | `String` | Query, Optional | A string that represents view state to protect against possible race conditions. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

viewsController.viewsUpdateAsync(token, null, null, null, null).thenAccept(result -> {
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
| Default | Typical error response. | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

