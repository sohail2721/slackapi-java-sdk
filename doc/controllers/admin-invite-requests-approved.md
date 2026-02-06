# Admin Invite Requests Approved

```java
AdminInviteRequestsApprovedController adminInviteRequestsApprovedController = client.getAdminInviteRequestsApprovedController();
```

## Class Name

`AdminInviteRequestsApprovedController`


# Admin Invite Requests Approved List

List all approved workspace invite requests.

API method documentation: [https://api.slack.com/methods/admin.inviteRequests.approved.list](https://api.slack.com/methods/admin.inviteRequests.approved.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminInviteRequestsApprovedListAsync(
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

adminInviteRequestsApprovedController.adminInviteRequestsApprovedListAsync(token, null, null, null).thenAccept(result -> {
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

