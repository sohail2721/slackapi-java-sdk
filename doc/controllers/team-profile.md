# Team Profile

```java
TeamProfileController teamProfileController = client.getTeamProfileController();
```

## Class Name

`TeamProfileController`


# Team Profile Get

Retrieve a team's profile.

API method documentation: [https://api.slack.com/methods/team.profile.get](https://api.slack.com/methods/team.profile.get)

```java
CompletableFuture<ApiResponse<TeamProfileGetSuccessSchema>> teamProfileGetAsync(
    final String token,
    final String visibility)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `users.profile:read` |
| `visibility` | `String` | Query, Optional | Filter by visibility. |

## Requires scope

### slackAuth

`users.profile:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`TeamProfileGetSuccessSchema`](../../doc/models/team-profile-get-success-schema.md).

## Example Usage

```java
String token = "token6";

teamProfileController.teamProfileGetAsync(token, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof TeamProfileGetErrorSchemaException) {
        TeamProfileGetErrorSchemaException teamProfileGetErrorSchemaException = (TeamProfileGetErrorSchemaException) cause;
        teamProfileGetErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`TeamProfileGetErrorSchemaException`](../../doc/models/team-profile-get-error-schema-exception.md) |

