# Admin Teams Admins

```java
AdminTeamsAdminsController adminTeamsAdminsController = client.getAdminTeamsAdminsController();
```

## Class Name

`AdminTeamsAdminsController`


# Admin Teams Admins List

List all of the admins on a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.admins.list](https://api.slack.com/methods/admin.teams.admins.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsAdminsListAsync(
    final String token,
    final String teamId,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin.teams:read` |
| `teamId` | `String` | Query, Required | - |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";

adminTeamsAdminsController.adminTeamsAdminsListAsync(token, teamId, null, null).thenAccept(result -> {
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

