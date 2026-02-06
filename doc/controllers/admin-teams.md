# Admin Teams

```java
AdminTeamsController adminTeamsController = client.getAdminTeamsController();
```

## Class Name

`AdminTeamsController`

## Methods

* [Admin Teams Create](../../doc/controllers/admin-teams.md#admin-teams-create)
* [Admin Teams List](../../doc/controllers/admin-teams.md#admin-teams-list)


# Admin Teams Create

Create an Enterprise team.

API method documentation: [https://api.slack.com/methods/admin.teams.create](https://api.slack.com/methods/admin.teams.create)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsCreateAsync(
    final String token,
    final String teamDomain,
    final String teamName,
    final String teamDescription,
    final String teamDiscoverability)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamDomain` | `String` | Form, Required | Team domain (for example, slacksoftballteam). |
| `teamName` | `String` | Form, Required | Team name (for example, Slack Softball Team). |
| `teamDescription` | `String` | Form, Optional | Description for the team. |
| `teamDiscoverability` | `String` | Form, Optional | Who can join the team. A team's discoverability can be `open`, `closed`, `invite_only`, or `unlisted`. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamDomain = "team_domain2";
String teamName = "team_name6";

adminTeamsController.adminTeamsCreateAsync(token, teamDomain, teamName, null, null).thenAccept(result -> {
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


# Admin Teams List

List all teams on an Enterprise organization

API method documentation: [https://api.slack.com/methods/admin.teams.list](https://api.slack.com/methods/admin.teams.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsListAsync(
    final String token,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.teams:read` |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Must be between 1 - 100 both inclusive. |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

adminTeamsController.adminTeamsListAsync(token, null, null).thenAccept(result -> {
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

