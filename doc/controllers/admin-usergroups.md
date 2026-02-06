# Admin Usergroups

```java
AdminUsergroupsController adminUsergroupsController = client.getAdminUsergroupsController();
```

## Class Name

`AdminUsergroupsController`

## Methods

* [Admin Usergroups Add Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-add-channels)
* [Admin Usergroups Add Teams](../../doc/controllers/admin-usergroups.md#admin-usergroups-add-teams)
* [Admin Usergroups List Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-list-channels)
* [Admin Usergroups Remove Channels](../../doc/controllers/admin-usergroups.md#admin-usergroups-remove-channels)


# Admin Usergroups Add Channels

Add one or more default channels to an IDP group.

API method documentation: [https://api.slack.com/methods/admin.usergroups.addChannels](https://api.slack.com/methods/admin.usergroups.addChannels)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsergroupsAddChannelsAsync(
    final String token,
    final String usergroupId,
    final String channelIds,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.usergroups:write` |
| `usergroupId` | `String` | Form, Required | ID of the IDP group to add default channels for. |
| `channelIds` | `String` | Form, Required | Comma separated string of channel IDs. |
| `teamId` | `String` | Form, Optional | The workspace to add default channels in. |

## Requires scope

### slackAuth

`admin.usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String usergroupId = "usergroup_id0";
String channelIds = "channel_ids8";

adminUsergroupsController.adminUsergroupsAddChannelsAsync(token, usergroupId, channelIds, null).thenAccept(result -> {
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Admin Usergroups Add Teams

Associate one or more default workspaces with an organization-wide IDP group.

API method documentation: [https://api.slack.com/methods/admin.usergroups.addTeams](https://api.slack.com/methods/admin.usergroups.addTeams)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsergroupsAddTeamsAsync(
    final String token,
    final String usergroupId,
    final String teamIds,
    final Boolean autoProvision)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `usergroupId` | `String` | Form, Required | An encoded usergroup (IDP Group) ID. |
| `teamIds` | `String` | Form, Required | A comma separated list of encoded team (workspace) IDs. Each workspace *MUST* belong to the organization associated with the token. |
| `autoProvision` | `Boolean` | Form, Optional | When `true`, this method automatically creates new workspace accounts for the IDP group members. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String usergroupId = "usergroup_id0";
String teamIds = "team_ids2";

adminUsergroupsController.adminUsergroupsAddTeamsAsync(token, usergroupId, teamIds, null).thenAccept(result -> {
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


# Admin Usergroups List Channels

List the channels linked to an org-level IDP group (user group).

API method documentation: [https://api.slack.com/methods/admin.usergroups.listChannels](https://api.slack.com/methods/admin.usergroups.listChannels)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsergroupsListChannelsAsync(
    final String token,
    final String usergroupId,
    final String teamId,
    final Boolean includeNumMembers)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.usergroups:read` |
| `usergroupId` | `String` | Query, Required | ID of the IDP group to list default channels for. |
| `teamId` | `String` | Query, Optional | ID of the the workspace. |
| `includeNumMembers` | `Boolean` | Query, Optional | Flag to include or exclude the count of members per channel. |

## Requires scope

### slackAuth

`admin.usergroups:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String usergroupId = "usergroup_id0";

adminUsergroupsController.adminUsergroupsListChannelsAsync(token, usergroupId, null, null).thenAccept(result -> {
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |


# Admin Usergroups Remove Channels

Remove one or more default channels from an org-level IDP group (user group).

API method documentation: [https://api.slack.com/methods/admin.usergroups.removeChannels](https://api.slack.com/methods/admin.usergroups.removeChannels)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminUsergroupsRemoveChannelsAsync(
    final String token,
    final String usergroupId,
    final String channelIds)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.usergroups:write` |
| `usergroupId` | `String` | Form, Required | ID of the IDP Group |
| `channelIds` | `String` | Form, Required | Comma-separated string of channel IDs |

## Requires scope

### slackAuth

`admin.usergroups:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String usergroupId = "usergroup_id0";
String channelIds = "channel_ids8";

adminUsergroupsController.adminUsergroupsRemoveChannelsAsync(token, usergroupId, channelIds).thenAccept(result -> {
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
| Default | Typical error response if the token provided is not associated with an Org Admin or Owner | [`DefaultErrorTemplateException`](../../doc/models/default-error-template-exception.md) |

