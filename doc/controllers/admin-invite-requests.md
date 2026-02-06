# Admin Invite Requests

```java
AdminInviteRequestsController adminInviteRequestsController = client.getAdminInviteRequestsController();
```

## Class Name

`AdminInviteRequestsController`

## Methods

* [Admin Invite Requests Approve](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-approve)
* [Admin Invite Requests Deny](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-deny)
* [Admin Invite Requests List](../../doc/controllers/admin-invite-requests.md#admin-invite-requests-list)


# Admin Invite Requests Approve

Approve a workspace invite request.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.approve](https://api.slack.com/methods/admin.inviteRequests.approve)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminInviteRequestsApproveAsync(
    final String token,
    final String inviteRequestId,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.invites:write` |
| `inviteRequestId` | `String` | Form, Required | ID of the request to invite. |
| `teamId` | `String` | Form, Optional | ID for the workspace where the invite request was made. |

## Requires scope

### slackAuth

`admin.invites:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String inviteRequestId = "invite_request_id4";

adminInviteRequestsController.adminInviteRequestsApproveAsync(token, inviteRequestId, null).thenAccept(result -> {
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


# Admin Invite Requests Deny

Deny a workspace invite request.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.deny](https://api.slack.com/methods/admin.inviteRequests.deny)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminInviteRequestsDenyAsync(
    final String token,
    final String inviteRequestId,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.invites:write` |
| `inviteRequestId` | `String` | Form, Required | ID of the request to invite. |
| `teamId` | `String` | Form, Optional | ID for the workspace where the invite request was made. |

## Requires scope

### slackAuth

`admin.invites:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String inviteRequestId = "invite_request_id4";

adminInviteRequestsController.adminInviteRequestsDenyAsync(token, inviteRequestId, null).thenAccept(result -> {
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


# Admin Invite Requests List

List all pending workspace invite requests.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.list](https://api.slack.com/methods/admin.inviteRequests.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminInviteRequestsListAsync(
    final String token,
    final String teamId,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.invites:read` |
| `teamId` | `String` | Query, Optional | ID for the workspace where the invite requests were made. |
| `cursor` | `String` | Query, Optional | Value of the `next_cursor` field sent as part of the previous API response |
| `limit` | `Integer` | Query, Optional | The number of results that will be returned by the API on each invocation. Must be between 1 - 1000, both inclusive |

## Requires scope

### slackAuth

`admin.invites:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

adminInviteRequestsController.adminInviteRequestsListAsync(token, null, null, null).thenAccept(result -> {
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

