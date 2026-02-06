# Calls Participants

```java
CallsParticipantsController callsParticipantsController = client.getCallsParticipantsController();
```

## Class Name

`CallsParticipantsController`

## Methods

* [Calls Participants Add](../../doc/controllers/calls-participants.md#calls-participants-add)
* [Calls Participants Remove](../../doc/controllers/calls-participants.md#calls-participants-remove)


# Calls Participants Add

Registers new participants added to a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.add](https://api.slack.com/methods/calls.participants.add)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> callsParticipantsAddAsync(
    final String token,
    final String id,
    final String users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `String` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `String` | Form, Required | The list of users to add as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String id = "id0";
String users = "users6";

callsParticipantsController.callsParticipantsAddAsync(token, id, users).thenAccept(result -> {
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


# Calls Participants Remove

Registers participants removed from a Call.

API method documentation: [https://api.slack.com/methods/calls.participants.remove](https://api.slack.com/methods/calls.participants.remove)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> callsParticipantsRemoveAsync(
    final String token,
    final String id,
    final String users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `calls:write` |
| `id` | `String` | Form, Required | `id` returned by the [`calls.add`](/methods/calls.add) method. |
| `users` | `String` | Form, Required | The list of users to remove as participants in the Call. [Read more on how to specify users here](/apis/calls#users). |

## Requires scope

### slackAuth

`calls:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String id = "id0";
String users = "users6";

callsParticipantsController.callsParticipantsRemoveAsync(token, id, users).thenAccept(result -> {
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

