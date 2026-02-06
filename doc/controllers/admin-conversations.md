# Admin Conversations

```java
AdminConversationsController adminConversationsController = client.getAdminConversationsController();
```

## Class Name

`AdminConversationsController`

## Methods

* [Admin Conversations Archive](../../doc/controllers/admin-conversations.md#admin-conversations-archive)
* [Admin Conversations Convert to Private](../../doc/controllers/admin-conversations.md#admin-conversations-convert-to-private)
* [Admin Conversations Create](../../doc/controllers/admin-conversations.md#admin-conversations-create)
* [Admin Conversations Delete](../../doc/controllers/admin-conversations.md#admin-conversations-delete)
* [Admin Conversations Disconnect Shared](../../doc/controllers/admin-conversations.md#admin-conversations-disconnect-shared)
* [Admin Conversations Get Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-get-conversation-prefs)
* [Admin Conversations Get Teams](../../doc/controllers/admin-conversations.md#admin-conversations-get-teams)
* [Admin Conversations Invite](../../doc/controllers/admin-conversations.md#admin-conversations-invite)
* [Admin Conversations Rename](../../doc/controllers/admin-conversations.md#admin-conversations-rename)
* [Admin Conversations Search](../../doc/controllers/admin-conversations.md#admin-conversations-search)
* [Admin Conversations Set Conversation Prefs](../../doc/controllers/admin-conversations.md#admin-conversations-set-conversation-prefs)
* [Admin Conversations Set Teams](../../doc/controllers/admin-conversations.md#admin-conversations-set-teams)
* [Admin Conversations Unarchive](../../doc/controllers/admin-conversations.md#admin-conversations-unarchive)


# Admin Conversations Archive

Archive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.archive](https://api.slack.com/methods/admin.conversations.archive)

```java
CompletableFuture<ApiResponse<AdminConversationsArchiveSchema>> adminConversationsArchiveAsync(
    final String token,
    final String channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The channel to archive. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsArchiveSchema`](../../doc/models/admin-conversations-archive-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsArchiveAsync(token, channelId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsArchiveErrorSchemaException) {
        AdminConversationsArchiveErrorSchemaException adminConversationsArchiveErrorSchemaException = (AdminConversationsArchiveErrorSchemaException) cause;
        adminConversationsArchiveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsArchiveErrorSchemaException`](../../doc/models/admin-conversations-archive-error-schema-exception.md) |


# Admin Conversations Convert to Private

Convert a public channel to a private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.convertToPrivate](https://api.slack.com/methods/admin.conversations.convertToPrivate)

```java
CompletableFuture<ApiResponse<AdminConversationsConvertToPrivateSchema>> adminConversationsConvertToPrivateAsync(
    final String token,
    final String channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The channel to convert to private. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsConvertToPrivateSchema`](../../doc/models/admin-conversations-convert-to-private-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsConvertToPrivateAsync(token, channelId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsConvertToPrivateErrorSchemaException) {
        AdminConversationsConvertToPrivateErrorSchemaException adminConversationsConvertToPrivateErrorSchemaException = (AdminConversationsConvertToPrivateErrorSchemaException) cause;
        adminConversationsConvertToPrivateErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsConvertToPrivateErrorSchemaException`](../../doc/models/admin-conversations-convert-to-private-error-schema-exception.md) |


# Admin Conversations Create

Create a public or private channel-based conversation.

API method documentation: [https://api.slack.com/methods/admin.conversations.create](https://api.slack.com/methods/admin.conversations.create)

```java
CompletableFuture<ApiResponse<AdminConversationsCreateSchema>> adminConversationsCreateAsync(
    final String token,
    final String name,
    final boolean isPrivate,
    final String description,
    final Boolean orgWide,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `name` | `String` | Form, Required | Name of the public or private channel to create. |
| `isPrivate` | `boolean` | Form, Required | When `true`, creates a private channel instead of a public channel |
| `description` | `String` | Form, Optional | Description of the public or private channel to create. |
| `orgWide` | `Boolean` | Form, Optional | When `true`, the channel will be available org-wide. Note: if the channel is not `org_wide=true`, you must specify a `team_id` for this channel |
| `teamId` | `String` | Form, Optional | The workspace to create the channel in. Note: this argument is required unless you set `org_wide=true`. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsCreateSchema`](../../doc/models/admin-conversations-create-schema.md).

## Example Usage

```java
String token = "token6";
String name = "name0";
boolean isPrivate = false;

adminConversationsController.adminConversationsCreateAsync(token, name, isPrivate, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsCreateErrorSchemaException) {
        AdminConversationsCreateErrorSchemaException adminConversationsCreateErrorSchemaException = (AdminConversationsCreateErrorSchemaException) cause;
        adminConversationsCreateErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsCreateErrorSchemaException`](../../doc/models/admin-conversations-create-error-schema-exception.md) |


# Admin Conversations Delete

Delete a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.delete](https://api.slack.com/methods/admin.conversations.delete)

```java
CompletableFuture<ApiResponse<AdminConversationsDeleteSchema>> adminConversationsDeleteAsync(
    final String token,
    final String channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The channel to delete. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsDeleteSchema`](../../doc/models/admin-conversations-delete-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsDeleteAsync(token, channelId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsDeleteErrorSchemaException) {
        AdminConversationsDeleteErrorSchemaException adminConversationsDeleteErrorSchemaException = (AdminConversationsDeleteErrorSchemaException) cause;
        adminConversationsDeleteErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsDeleteErrorSchemaException`](../../doc/models/admin-conversations-delete-error-schema-exception.md) |


# Admin Conversations Disconnect Shared

Disconnect a connected channel from one or more workspaces.

API method documentation: [https://api.slack.com/methods/admin.conversations.disconnectShared](https://api.slack.com/methods/admin.conversations.disconnectShared)

```java
CompletableFuture<ApiResponse<AdminConversationsRenameSchema>> adminConversationsDisconnectSharedAsync(
    final String token,
    final String channelId,
    final String leavingTeamIds)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The channel to be disconnected from some workspaces. |
| `leavingTeamIds` | `String` | Form, Optional | The team to be removed from the channel. Currently only a single team id can be specified. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsRenameSchema`](../../doc/models/admin-conversations-rename-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsDisconnectSharedAsync(token, channelId, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsDisconnectSharedErrorSchemaException) {
        AdminConversationsDisconnectSharedErrorSchemaException adminConversationsDisconnectSharedErrorSchemaException = (AdminConversationsDisconnectSharedErrorSchemaException) cause;
        adminConversationsDisconnectSharedErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsDisconnectSharedErrorSchemaException`](../../doc/models/admin-conversations-disconnect-shared-error-schema-exception.md) |


# Admin Conversations Get Conversation Prefs

Get conversation preferences for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.getConversationPrefs](https://api.slack.com/methods/admin.conversations.getConversationPrefs)

```java
CompletableFuture<ApiResponse<AdminConversationsGetConversationPrefsSchema>> adminConversationsGetConversationPrefsAsync(
    final String token,
    final String channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `String` | Query, Required | The channel to get preferences for. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsGetConversationPrefsSchema`](../../doc/models/admin-conversations-get-conversation-prefs-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsGetConversationPrefsAsync(token, channelId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsUnarchiveErrorSchemaException) {
        AdminConversationsUnarchiveErrorSchemaException adminConversationsUnarchiveErrorSchemaException = (AdminConversationsUnarchiveErrorSchemaException) cause;
        adminConversationsUnarchiveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchemaException`](../../doc/models/admin-conversations-unarchive-error-schema-exception.md) |


# Admin Conversations Get Teams

Get all the workspaces a given public or private channel is connected to within this Enterprise org.

API method documentation: [https://api.slack.com/methods/admin.conversations.getTeams](https://api.slack.com/methods/admin.conversations.getTeams)

```java
CompletableFuture<ApiResponse<AdminConversationsGetTeamsSchema>> adminConversationsGetTeamsAsync(
    final String token,
    final String channelId,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelId` | `String` | Query, Required | The channel to determine connected workspaces within the organization for. |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsGetTeamsSchema`](../../doc/models/admin-conversations-get-teams-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsGetTeamsAsync(token, channelId, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsGetTeamsErrorSchemaException) {
        AdminConversationsGetTeamsErrorSchemaException adminConversationsGetTeamsErrorSchemaException = (AdminConversationsGetTeamsErrorSchemaException) cause;
        adminConversationsGetTeamsErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsGetTeamsErrorSchemaException`](../../doc/models/admin-conversations-get-teams-error-schema-exception.md) |


# Admin Conversations Invite

Invite a user to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.invite](https://api.slack.com/methods/admin.conversations.invite)

```java
CompletableFuture<ApiResponse<AdminConversationsInviteSchema>> adminConversationsInviteAsync(
    final String token,
    final String userIds,
    final String channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `userIds` | `String` | Form, Required | The users to invite. |
| `channelId` | `String` | Form, Required | The channel that the users will be invited to. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsInviteSchema`](../../doc/models/admin-conversations-invite-schema.md).

## Example Usage

```java
String token = "token6";
String userIds = "user_ids4";
String channelId = "channel_id4";

adminConversationsController.adminConversationsInviteAsync(token, userIds, channelId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsInviteErrorSchemaException) {
        AdminConversationsInviteErrorSchemaException adminConversationsInviteErrorSchemaException = (AdminConversationsInviteErrorSchemaException) cause;
        adminConversationsInviteErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsInviteErrorSchemaException`](../../doc/models/admin-conversations-invite-error-schema-exception.md) |


# Admin Conversations Rename

Rename a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.rename](https://api.slack.com/methods/admin.conversations.rename)

```java
CompletableFuture<ApiResponse<AdminConversationsRenameSchema1>> adminConversationsRenameAsync(
    final String token,
    final String channelId,
    final String name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The channel to rename. |
| `name` | `String` | Form, Required | - |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsRenameSchema1`](../../doc/models/admin-conversations-rename-schema-1.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";
String name = "name0";

adminConversationsController.adminConversationsRenameAsync(token, channelId, name).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsUnarchiveErrorSchema2Exception) {
        AdminConversationsUnarchiveErrorSchema2Exception adminConversationsUnarchiveErrorSchema2Exception = (AdminConversationsUnarchiveErrorSchema2Exception) cause;
        adminConversationsUnarchiveErrorSchema2Exception.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema2Exception`](../../doc/models/admin-conversations-unarchive-error-schema-2-exception.md) |


# Admin Conversations Search

Search for public or private channels in an Enterprise organization.

API method documentation: [https://api.slack.com/methods/admin.conversations.search](https://api.slack.com/methods/admin.conversations.search)

```java
CompletableFuture<ApiResponse<AdminConversationsSearchSchema>> adminConversationsSearchAsync(
    final String token,
    final String teamIds,
    final String query,
    final Integer limit,
    final String cursor,
    final String searchChannelTypes,
    final String sort,
    final String sortDir)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `teamIds` | `String` | Query, Optional | Comma separated string of team IDs, signifying the workspaces to search through. |
| `query` | `String` | Query, Optional | Name of the the channel to query by. |
| `limit` | `Integer` | Query, Optional | Maximum number of items to be returned. Must be between 1 - 20 both inclusive. Default is 10. |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |
| `searchChannelTypes` | `String` | Query, Optional | The type of channel to include or exclude in the search. For example `private` will search private channels, while `private_exclude` will exclude them. For a full list of types, check the [Types section](#types). |
| `sort` | `String` | Query, Optional | Possible values are `relevant` (search ranking based on what we think is closest), `name` (alphabetical), `member_count` (number of users in the channel), and `created` (date channel was created). You can optionally pair this with the `sort_dir` arg to change how it is sorted |
| `sortDir` | `String` | Query, Optional | Sort direction. Possible values are `asc` for ascending order like (1, 2, 3) or (a, b, c), and `desc` for descending order like (3, 2, 1) or (c, b, a) |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsSearchSchema`](../../doc/models/admin-conversations-search-schema.md).

## Example Usage

```java
String token = "token6";

adminConversationsController.adminConversationsSearchAsync(token, null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsSearchErrorSchemaException) {
        AdminConversationsSearchErrorSchemaException adminConversationsSearchErrorSchemaException = (AdminConversationsSearchErrorSchemaException) cause;
        adminConversationsSearchErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsSearchErrorSchemaException`](../../doc/models/admin-conversations-search-error-schema-exception.md) |


# Admin Conversations Set Conversation Prefs

Set the posting permissions for a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setConversationPrefs](https://api.slack.com/methods/admin.conversations.setConversationPrefs)

```java
CompletableFuture<ApiResponse<AdminConversationsSetConversationPrefsSchema>> adminConversationsSetConversationPrefsAsync(
    final String token,
    final String channelId,
    final String prefs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The channel to set the prefs for |
| `prefs` | `String` | Form, Required | The prefs for this channel in a stringified JSON format. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsSetConversationPrefsSchema`](../../doc/models/admin-conversations-set-conversation-prefs-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";
String prefs = "prefs0";

adminConversationsController.adminConversationsSetConversationPrefsAsync(token, channelId, prefs).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsSetConversationPrefsErrorSchemaException) {
        AdminConversationsSetConversationPrefsErrorSchemaException adminConversationsSetConversationPrefsErrorSchemaException = (AdminConversationsSetConversationPrefsErrorSchemaException) cause;
        adminConversationsSetConversationPrefsErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsSetConversationPrefsErrorSchemaException`](../../doc/models/admin-conversations-set-conversation-prefs-error-schema-exception.md) |


# Admin Conversations Set Teams

Set the workspaces in an Enterprise grid org that connect to a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.setTeams](https://api.slack.com/methods/admin.conversations.setTeams)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminConversationsSetTeamsAsync(
    final String token,
    final String channelId,
    final String teamId,
    final String targetTeamIds,
    final Boolean orgChannel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The encoded `channel_id` to add or remove to workspaces. |
| `teamId` | `String` | Form, Optional | The workspace to which the channel belongs. Omit this argument if the channel is a cross-workspace shared channel. |
| `targetTeamIds` | `String` | Form, Optional | A comma-separated list of workspaces to which the channel should be shared. Not required if the channel is being shared org-wide. |
| `orgChannel` | `Boolean` | Form, Optional | True if channel has to be converted to an org channel |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsSetTeamsAsync(token, channelId, null, null, null).thenAccept(result -> {
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


# Admin Conversations Unarchive

Unarchive a public or private channel.

API method documentation: [https://api.slack.com/methods/admin.conversations.unarchive](https://api.slack.com/methods/admin.conversations.unarchive)

```java
CompletableFuture<ApiResponse<AdminConversationsUnarchiveSchema>> adminConversationsUnarchiveAsync(
    final String token,
    final String channelId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.conversations:write` |
| `channelId` | `String` | Form, Required | The channel to unarchive. |

## Requires scope

### slackAuth

`admin.conversations:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AdminConversationsUnarchiveSchema`](../../doc/models/admin-conversations-unarchive-schema.md).

## Example Usage

```java
String token = "token6";
String channelId = "channel_id4";

adminConversationsController.adminConversationsUnarchiveAsync(token, channelId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AdminConversationsUnarchiveErrorSchema3Exception) {
        AdminConversationsUnarchiveErrorSchema3Exception adminConversationsUnarchiveErrorSchema3Exception = (AdminConversationsUnarchiveErrorSchema3Exception) cause;
        adminConversationsUnarchiveErrorSchema3Exception.printStackTrace();
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
| Default | Typical error response | [`AdminConversationsUnarchiveErrorSchema3Exception`](../../doc/models/admin-conversations-unarchive-error-schema-3-exception.md) |

