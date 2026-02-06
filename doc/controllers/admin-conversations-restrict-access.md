# Admin Conversations Restrict Access

```java
AdminConversationsRestrictAccessController adminConversationsRestrictAccessController = client.getAdminConversationsRestrictAccessController();
```

## Class Name

`AdminConversationsRestrictAccessController`

## Methods

* [Admin Conversations Restrict Access Add Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-add-group)
* [Admin Conversations Restrict Access List Groups](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-list-groups)
* [Admin Conversations Restrict Access Remove Group](../../doc/controllers/admin-conversations-restrict-access.md#admin-conversations-restrict-access-remove-group)


# Admin Conversations Restrict Access Add Group

Add an allowlist of IDP groups for accessing a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.addGroup)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminConversationsRestrictAccessAddGroupAsync(
    final String token,
    final String groupId,
    final String channelId,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `groupId` | `String` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to be an allowlist for the private channel. |
| `channelId` | `String` | Form, Required | The channel to link this group to. |
| `teamId` | `String` | Form, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String groupId = "group_id0";
String channelId = "channel_id4";

adminConversationsRestrictAccessController.adminConversationsRestrictAccessAddGroupAsync(token, groupId, channelId, null).thenAccept(result -> {
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


# Admin Conversations Restrict Access List Groups

List all IDP Groups linked to a channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups](https://api.slack.com/methods/admin.conversations.restrictAccess.listGroups)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminConversationsRestrictAccessListGroupsAsync(
    final String token,
    final String channelId,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `String` | Query, Required | - |
| `teamId` | `String` | Query, Optional | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsRestrictAccessController.adminConversationsRestrictAccessListGroupsAsync(token, channelId, null).thenAccept(result -> {
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


# Admin Conversations Restrict Access Remove Group

Remove a linked IDP group linked from a private channel

API method documentation: [https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup](https://api.slack.com/methods/admin.conversations.restrictAccess.removeGroup)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminConversationsRestrictAccessRemoveGroupAsync(
    final String token,
    final String teamId,
    final String groupId,
    final String channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `teamId` | `String` | Form, Required | The workspace where the channel exists. This argument is required for channels only tied to one workspace, and optional for channels that are shared across an organization. |
| `groupId` | `String` | Form, Required | The [IDP Group](https://slack.com/help/articles/115001435788-Connect-identity-provider-groups-to-your-Enterprise-Grid-org) ID to remove from the private channel. |
| `channelId` | `String` | Form, Required | The channel to remove the linked group from. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String groupId = "group_id0";
String channelId = "channel_id4";

adminConversationsRestrictAccessController.adminConversationsRestrictAccessRemoveGroupAsync(token, teamId, groupId, channelId).thenAccept(result -> {
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

