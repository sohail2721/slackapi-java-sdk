# Calls

```java
CallsController callsController = client.getCallsController();
```

## Class Name

`CallsController`

## Methods

* [Calls Add](../../doc/controllers/calls.md#calls-add)
* [Calls End](../../doc/controllers/calls.md#calls-end)
* [Calls Info](../../doc/controllers/calls.md#calls-info)
* [Calls Update](../../doc/controllers/calls.md#calls-update)


# Calls Add

Registers a new Call.

API method documentation: [https://api.slack.com/methods/calls.add](https://api.slack.com/methods/calls.add)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> callsAddAsync(
    final String token,
    final String externalUniqueId,
    final String joinUrl,
    final String externalDisplayId,
    final String desktopAppJoinUrl,
    final Integer dateStart,
    final String title,
    final String createdBy,
    final String users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `externalUniqueId` | `String` | Form, Required | An ID supplied by the 3rd-party Call provider. It must be unique across all Calls from that service. |
| `joinUrl` | `String` | Form, Required | The URL required for a client to join the Call. |
| `externalDisplayId` | `String` | Form, Optional | An optional, human-readable ID supplied by the 3rd-party Call provider. If supplied, this ID will be displayed in the Call object. |
| `desktopAppJoinUrl` | `String` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |
| `dateStart` | `Integer` | Form, Optional | Call start time in UTC UNIX timestamp format |
| `title` | `String` | Form, Optional | The name of the Call. |
| `createdBy` | `String` | Form, Optional | The valid Slack user ID of the user who created this Call. When this method is called with a user token, the `created_by` field is optional and defaults to the authed user of the token. Otherwise, the field is required. |
| `users` | `String` | Form, Optional | The list of users to register as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String externalUniqueId = "external_unique_id0";
String joinUrl = "join_url6";

callsController.callsAddAsync(token, externalUniqueId, joinUrl, null, null, null, null, null, null).thenAccept(result -> {
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


# Calls End

Ends a Call.

API method documentation: [https://api.slack.com/methods/calls.end](https://api.slack.com/methods/calls.end)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> callsEndAsync(
    final String token,
    final String id,
    final Integer duration)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `String` | Form, Required | `id` returned when registering the call using the [`calls.add`](/methods/calls.add) method. |
| `duration` | `Integer` | Form, Optional | Call duration in seconds |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String id = "id0";

callsController.callsEndAsync(token, id, null).thenAccept(result -> {
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


# Calls Info

Returns information about a Call.

API method documentation: [https://api.slack.com/methods/calls.info](https://api.slack.com/methods/calls.info)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> callsInfoAsync(
    final String token,
    final String id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `calls:read` |
| `id` | `String` | Query, Required | `id` of the Call returned by the [`calls.add`](/methods/calls.add) method. |

## Requires scope

### slackAuth

`calls:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String id = "id0";

callsController.callsInfoAsync(token, id).thenAccept(result -> {
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


# Calls Update

Updates information about a Call.

API method documentation: [https://api.slack.com/methods/calls.update](https://api.slack.com/methods/calls.update)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> callsUpdateAsync(
    final String token,
    final String id,
    final String title,
    final String joinUrl,
    final String desktopAppJoinUrl)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `String` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `title` | `String` | Form, Optional | The name of the Call. |
| `joinUrl` | `String` | Form, Optional | The URL required for a client to join the Call. |
| `desktopAppJoinUrl` | `String` | Form, Optional | When supplied, available Slack clients will attempt to directly launch the 3rd-party Call with this URL. |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String id = "id0";

callsController.callsUpdateAsync(token, id, null, null, null).thenAccept(result -> {
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

