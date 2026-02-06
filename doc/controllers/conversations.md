# Conversations

```java
ConversationsController conversationsController = client.getConversationsController();
```

## Class Name

`ConversationsController`

## Methods

* [Conversations Archive](../../doc/controllers/conversations.md#conversations-archive)
* [Conversations Close](../../doc/controllers/conversations.md#conversations-close)
* [Conversations Create](../../doc/controllers/conversations.md#conversations-create)
* [Conversations History](../../doc/controllers/conversations.md#conversations-history)
* [Conversations Info](../../doc/controllers/conversations.md#conversations-info)
* [Conversations Invite](../../doc/controllers/conversations.md#conversations-invite)
* [Conversations Join](../../doc/controllers/conversations.md#conversations-join)
* [Conversations Kick](../../doc/controllers/conversations.md#conversations-kick)
* [Conversations Leave](../../doc/controllers/conversations.md#conversations-leave)
* [Conversations List](../../doc/controllers/conversations.md#conversations-list)
* [Conversations Mark](../../doc/controllers/conversations.md#conversations-mark)
* [Conversations Members](../../doc/controllers/conversations.md#conversations-members)
* [Conversations Open](../../doc/controllers/conversations.md#conversations-open)
* [Conversations Rename](../../doc/controllers/conversations.md#conversations-rename)
* [Conversations Replies](../../doc/controllers/conversations.md#conversations-replies)
* [Conversations Set Purpose](../../doc/controllers/conversations.md#conversations-set-purpose)
* [Conversations Set Topic](../../doc/controllers/conversations.md#conversations-set-topic)
* [Conversations Unarchive](../../doc/controllers/conversations.md#conversations-unarchive)


# Conversations Archive

Archives a conversation.

API method documentation: [https://api.slack.com/methods/conversations.archive](https://api.slack.com/methods/conversations.archive)

```java
CompletableFuture<ApiResponse<ConversationsArchiveSuccessSchema>> conversationsArchiveAsync(
    final String token,
    final String channel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | ID of conversation to archive |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsArchiveSuccessSchema`](../../doc/models/conversations-archive-success-schema.md).

## Example Usage

```java
conversationsController.conversationsArchiveAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsArchiveErrorSchemaException) {
        ConversationsArchiveErrorSchemaException conversationsArchiveErrorSchemaException = (ConversationsArchiveErrorSchemaException) cause;
        conversationsArchiveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsArchiveErrorSchemaException`](../../doc/models/conversations-archive-error-schema-exception.md) |


# Conversations Close

Closes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.close](https://api.slack.com/methods/conversations.close)

```java
CompletableFuture<ApiResponse<ConversationsCloseSuccessSchema>> conversationsCloseAsync(
    final String token,
    final String channel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | Conversation to close. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsCloseSuccessSchema`](../../doc/models/conversations-close-success-schema.md).

## Example Usage

```java
conversationsController.conversationsCloseAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsCloseErrorSchemaException) {
        ConversationsCloseErrorSchemaException conversationsCloseErrorSchemaException = (ConversationsCloseErrorSchemaException) cause;
        conversationsCloseErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsCloseErrorSchemaException`](../../doc/models/conversations-close-error-schema-exception.md) |


# Conversations Create

Initiates a public or private channel-based conversation

API method documentation: [https://api.slack.com/methods/conversations.create](https://api.slack.com/methods/conversations.create)

```java
CompletableFuture<ApiResponse<ConversationsCreateSuccessSchema>> conversationsCreateAsync(
    final String token,
    final String name,
    final Boolean isPrivate)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `name` | `String` | Form, Optional | Name of the public or private channel to create |
| `isPrivate` | `Boolean` | Form, Optional | Create a private channel instead of a public one |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsCreateSuccessSchema`](../../doc/models/conversations-create-success-schema.md).

## Example Usage

```java
conversationsController.conversationsCreateAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsCreateErrorSchemaException) {
        ConversationsCreateErrorSchemaException conversationsCreateErrorSchemaException = (ConversationsCreateErrorSchemaException) cause;
        conversationsCreateErrorSchemaException.printStackTrace();
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
| Default | Typical error response when name already in use | [`ConversationsCreateErrorSchemaException`](../../doc/models/conversations-create-error-schema-exception.md) |


# Conversations History

Fetches a conversation's history of messages and events.

API method documentation: [https://api.slack.com/methods/conversations.history](https://api.slack.com/methods/conversations.history)

```java
CompletableFuture<ApiResponse<ConversationsHistorySuccessSchema>> conversationsHistoryAsync(
    final String token,
    final String channel,
    final Double latest,
    final Double oldest,
    final Boolean inclusive,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `String` | Query, Optional | Conversation ID to fetch history for. |
| `latest` | `Double` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `Double` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `Boolean` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsHistorySuccessSchema`](../../doc/models/conversations-history-success-schema.md).

## Example Usage

```java
conversationsController.conversationsHistoryAsync(null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsHistoryErrorSchemaException) {
        ConversationsHistoryErrorSchemaException conversationsHistoryErrorSchemaException = (ConversationsHistoryErrorSchemaException) cause;
        conversationsHistoryErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsHistoryErrorSchemaException`](../../doc/models/conversations-history-error-schema-exception.md) |


# Conversations Info

Retrieve information about a conversation.

API method documentation: [https://api.slack.com/methods/conversations.info](https://api.slack.com/methods/conversations.info)

```java
CompletableFuture<ApiResponse<ConversationsInfoSuccessSchema>> conversationsInfoAsync(
    final String token,
    final String channel,
    final Boolean includeLocale,
    final Boolean includeNumMembers)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `String` | Query, Optional | Conversation ID to learn more about |
| `includeLocale` | `Boolean` | Query, Optional | Set this to `true` to receive the locale for this conversation. Defaults to `false` |
| `includeNumMembers` | `Boolean` | Query, Optional | Set to `true` to include the member count for the specified conversation. Defaults to `false` |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsInfoSuccessSchema`](../../doc/models/conversations-info-success-schema.md).

## Example Usage

```java
conversationsController.conversationsInfoAsync(null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsInfoErrorSchemaException) {
        ConversationsInfoErrorSchemaException conversationsInfoErrorSchemaException = (ConversationsInfoErrorSchemaException) cause;
        conversationsInfoErrorSchemaException.printStackTrace();
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
| Default | Typical error response when a channel cannot be found | [`ConversationsInfoErrorSchemaException`](../../doc/models/conversations-info-error-schema-exception.md) |


# Conversations Invite

Invites users to a channel.

API method documentation: [https://api.slack.com/methods/conversations.invite](https://api.slack.com/methods/conversations.invite)

```java
CompletableFuture<ApiResponse<ConversationsInviteErrorSchema>> conversationsInviteAsync(
    final String token,
    final String channel,
    final String users)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | The ID of the public or private channel to invite user(s) to. |
| `users` | `String` | Form, Optional | A comma separated list of user IDs. Up to 1000 users may be listed. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsInviteErrorSchema`](../../doc/models/conversations-invite-error-schema.md).

## Example Usage

```java
conversationsController.conversationsInviteAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsInviteErrorSchema1Exception) {
        ConversationsInviteErrorSchema1Exception conversationsInviteErrorSchema1Exception = (ConversationsInviteErrorSchema1Exception) cause;
        conversationsInviteErrorSchema1Exception.printStackTrace();
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
| Default | Typical error response when an invite is attempted on a conversation type that does not support it | [`ConversationsInviteErrorSchema1Exception`](../../doc/models/conversations-invite-error-schema-1-exception.md) |


# Conversations Join

Joins an existing conversation.

API method documentation: [https://api.slack.com/methods/conversations.join](https://api.slack.com/methods/conversations.join)

```java
CompletableFuture<ApiResponse<ConversationsJoinSuccessSchema>> conversationsJoinAsync(
    final String token,
    final String channel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `channels:write` |
| `channel` | `String` | Form, Optional | ID of conversation to join |

## Requires scope

### slackAuth

`channels:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsJoinSuccessSchema`](../../doc/models/conversations-join-success-schema.md).

## Example Usage

```java
conversationsController.conversationsJoinAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsJoinErrorSchemaException) {
        ConversationsJoinErrorSchemaException conversationsJoinErrorSchemaException = (ConversationsJoinErrorSchemaException) cause;
        conversationsJoinErrorSchemaException.printStackTrace();
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
| Default | Typical error response if the conversation is archived and cannot be joined | [`ConversationsJoinErrorSchemaException`](../../doc/models/conversations-join-error-schema-exception.md) |


# Conversations Kick

Removes a user from a conversation.

API method documentation: [https://api.slack.com/methods/conversations.kick](https://api.slack.com/methods/conversations.kick)

```java
CompletableFuture<ApiResponse<ConversationsKickSuccessSchema>> conversationsKickAsync(
    final String token,
    final String channel,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | ID of conversation to remove user from. |
| `user` | `String` | Form, Optional | User ID to be removed. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsKickSuccessSchema`](../../doc/models/conversations-kick-success-schema.md).

## Example Usage

```java
conversationsController.conversationsKickAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsKickErrorSchemaException) {
        ConversationsKickErrorSchemaException conversationsKickErrorSchemaException = (ConversationsKickErrorSchemaException) cause;
        conversationsKickErrorSchemaException.printStackTrace();
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
| Default | Typical error response when you attempt to kick yourself from a channel | [`ConversationsKickErrorSchemaException`](../../doc/models/conversations-kick-error-schema-exception.md) |


# Conversations Leave

Leaves a conversation.

API method documentation: [https://api.slack.com/methods/conversations.leave](https://api.slack.com/methods/conversations.leave)

```java
CompletableFuture<ApiResponse<ConversationsLeaveSuccessSchema>> conversationsLeaveAsync(
    final String token,
    final String channel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | Conversation to leave |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsLeaveSuccessSchema`](../../doc/models/conversations-leave-success-schema.md).

## Example Usage

```java
conversationsController.conversationsLeaveAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsLeaveErrorSchemaException) {
        ConversationsLeaveErrorSchemaException conversationsLeaveErrorSchemaException = (ConversationsLeaveErrorSchemaException) cause;
        conversationsLeaveErrorSchemaException.printStackTrace();
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
| Default | Typical error response when attempting to leave a workspace's "general" channel | [`ConversationsLeaveErrorSchemaException`](../../doc/models/conversations-leave-error-schema-exception.md) |


# Conversations List

Lists all channels in a Slack team.

API method documentation: [https://api.slack.com/methods/conversations.list](https://api.slack.com/methods/conversations.list)

```java
CompletableFuture<ApiResponse<ConversationsListSuccessSchema>> conversationsListAsync(
    final String token,
    final Boolean excludeArchived,
    final String types,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `excludeArchived` | `Boolean` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `types` | `String` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsListSuccessSchema`](../../doc/models/conversations-list-success-schema.md).

## Example Usage

```java
conversationsController.conversationsListAsync(null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsListErrorSchemaException) {
        ConversationsListErrorSchemaException conversationsListErrorSchemaException = (ConversationsListErrorSchemaException) cause;
        conversationsListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsListErrorSchemaException`](../../doc/models/conversations-list-error-schema-exception.md) |


# Conversations Mark

Sets the read cursor in a channel.

API method documentation: [https://api.slack.com/methods/conversations.mark](https://api.slack.com/methods/conversations.mark)

```java
CompletableFuture<ApiResponse<ConversationsMarkSuccessSchema>> conversationsMarkAsync(
    final String token,
    final String channel,
    final Double ts)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | Channel or conversation to set the read cursor for. |
| `ts` | `Double` | Form, Optional | Unique identifier of message you want marked as most recently seen in this conversation. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsMarkSuccessSchema`](../../doc/models/conversations-mark-success-schema.md).

## Example Usage

```java
conversationsController.conversationsMarkAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsMarkErrorSchemaException) {
        ConversationsMarkErrorSchemaException conversationsMarkErrorSchemaException = (ConversationsMarkErrorSchemaException) cause;
        conversationsMarkErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsMarkErrorSchemaException`](../../doc/models/conversations-mark-error-schema-exception.md) |


# Conversations Members

Retrieve members of a conversation.

API method documentation: [https://api.slack.com/methods/conversations.members](https://api.slack.com/methods/conversations.members)

```java
CompletableFuture<ApiResponse<ConversationsMembersSuccessSchema>> conversationsMembersAsync(
    final String token,
    final String channel,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `channel` | `String` | Query, Optional | ID of the conversation to retrieve members for |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsMembersSuccessSchema`](../../doc/models/conversations-members-success-schema.md).

## Example Usage

```java
conversationsController.conversationsMembersAsync(null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsMembersErrorSchemaException) {
        ConversationsMembersErrorSchemaException conversationsMembersErrorSchemaException = (ConversationsMembersErrorSchemaException) cause;
        conversationsMembersErrorSchemaException.printStackTrace();
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
| Default | Typical error response when an invalid cursor is provided | [`ConversationsMembersErrorSchemaException`](../../doc/models/conversations-members-error-schema-exception.md) |


# Conversations Open

Opens or resumes a direct message or multi-person direct message.

API method documentation: [https://api.slack.com/methods/conversations.open](https://api.slack.com/methods/conversations.open)

```java
CompletableFuture<ApiResponse<ConversationsOpenSuccessSchema>> conversationsOpenAsync(
    final String token,
    final String channel,
    final String users,
    final Boolean returnIm)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | Resume a conversation by supplying an `im` or `mpim`'s ID. Or provide the `users` field instead. |
| `users` | `String` | Form, Optional | Comma separated lists of users. If only one user is included, this creates a 1:1 DM.  The ordering of the users is preserved whenever a multi-person direct message is returned. Supply a `channel` when not supplying `users`. |
| `returnIm` | `Boolean` | Form, Optional | Boolean, indicates you want the full IM channel definition in the response. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsOpenSuccessSchema`](../../doc/models/conversations-open-success-schema.md).

## Example Usage

```java
conversationsController.conversationsOpenAsync(null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsOpenErrorSchemaException) {
        ConversationsOpenErrorSchemaException conversationsOpenErrorSchemaException = (ConversationsOpenErrorSchemaException) cause;
        conversationsOpenErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsOpenErrorSchemaException`](../../doc/models/conversations-open-error-schema-exception.md) |


# Conversations Rename

Renames a conversation.

API method documentation: [https://api.slack.com/methods/conversations.rename](https://api.slack.com/methods/conversations.rename)

```java
CompletableFuture<ApiResponse<ConversationsRenameSuccessSchema>> conversationsRenameAsync(
    final String token,
    final String channel,
    final String name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | ID of conversation to rename |
| `name` | `String` | Form, Optional | New name for conversation. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsRenameSuccessSchema`](../../doc/models/conversations-rename-success-schema.md).

## Example Usage

```java
conversationsController.conversationsRenameAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsRenameErrorSchemaException) {
        ConversationsRenameErrorSchemaException conversationsRenameErrorSchemaException = (ConversationsRenameErrorSchemaException) cause;
        conversationsRenameErrorSchemaException.printStackTrace();
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
| Default | Typical error response when the calling user is not a member of the conversation | [`ConversationsRenameErrorSchemaException`](../../doc/models/conversations-rename-error-schema-exception.md) |


# Conversations Replies

Retrieve a thread of messages posted to a conversation

API method documentation: [https://api.slack.com/methods/conversations.replies](https://api.slack.com/methods/conversations.replies)

```java
CompletableFuture<ApiResponse<ConversationsRepliesSuccessSchema>> conversationsRepliesAsync(
    final String token,
    final String channel,
    final Double ts,
    final Double latest,
    final Double oldest,
    final Boolean inclusive,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `conversations:history` |
| `channel` | `String` | Query, Optional | Conversation ID to fetch thread from. |
| `ts` | `Double` | Query, Optional | Unique identifier of a thread's parent message. `ts` must be the timestamp of an existing message with 0 or more replies. If there are no replies then just the single message referenced by `ts` will return - it is just an ordinary, unthreaded message. |
| `latest` | `Double` | Query, Optional | End of time range of messages to include in results. |
| `oldest` | `Double` | Query, Optional | Start of time range of messages to include in results. |
| `inclusive` | `Boolean` | Query, Optional | Include messages with latest or oldest timestamp in results only when either timestamp is specified. |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:history`, `groups:history`, `im:history`, `mpim:history`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsRepliesSuccessSchema`](../../doc/models/conversations-replies-success-schema.md).

## Example Usage

```java
conversationsController.conversationsRepliesAsync(null, null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsRepliesErrorSchemaException) {
        ConversationsRepliesErrorSchemaException conversationsRepliesErrorSchemaException = (ConversationsRepliesErrorSchemaException) cause;
        conversationsRepliesErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsRepliesErrorSchemaException`](../../doc/models/conversations-replies-error-schema-exception.md) |


# Conversations Set Purpose

Sets the purpose for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setPurpose](https://api.slack.com/methods/conversations.setPurpose)

```java
CompletableFuture<ApiResponse<ConversationsSetPurposeSuccessSchema>> conversationsSetPurposeAsync(
    final String token,
    final String channel,
    final String purpose)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | Conversation to set the purpose of |
| `purpose` | `String` | Form, Optional | A new, specialer purpose |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsSetPurposeSuccessSchema`](../../doc/models/conversations-set-purpose-success-schema.md).

## Example Usage

```java
conversationsController.conversationsSetPurposeAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsSetPurposeErrorSchemaException) {
        ConversationsSetPurposeErrorSchemaException conversationsSetPurposeErrorSchemaException = (ConversationsSetPurposeErrorSchemaException) cause;
        conversationsSetPurposeErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsSetPurposeErrorSchemaException`](../../doc/models/conversations-set-purpose-error-schema-exception.md) |


# Conversations Set Topic

Sets the topic for a conversation.

API method documentation: [https://api.slack.com/methods/conversations.setTopic](https://api.slack.com/methods/conversations.setTopic)

```java
CompletableFuture<ApiResponse<ConversationsSetTopicSuccessSchema>> conversationsSetTopicAsync(
    final String token,
    final String channel,
    final String topic)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | Conversation to set the topic of |
| `topic` | `String` | Form, Optional | The new topic string. Does not support formatting or linkification. |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsSetTopicSuccessSchema`](../../doc/models/conversations-set-topic-success-schema.md).

## Example Usage

```java
conversationsController.conversationsSetTopicAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsSetTopicErrorSchemaException) {
        ConversationsSetTopicErrorSchemaException conversationsSetTopicErrorSchemaException = (ConversationsSetTopicErrorSchemaException) cause;
        conversationsSetTopicErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsSetTopicErrorSchemaException`](../../doc/models/conversations-set-topic-error-schema-exception.md) |


# Conversations Unarchive

Reverses conversation archival.

API method documentation: [https://api.slack.com/methods/conversations.unarchive](https://api.slack.com/methods/conversations.unarchive)

```java
CompletableFuture<ApiResponse<ConversationsUnarchiveSuccessSchema>> conversationsUnarchiveAsync(
    final String token,
    final String channel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `conversations:write` |
| `channel` | `String` | Form, Optional | ID of conversation to unarchive |

## Requires scope

### slackAuth

`channels:write`, `groups:write`, `im:write`, `mpim:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ConversationsUnarchiveSuccessSchema`](../../doc/models/conversations-unarchive-success-schema.md).

## Example Usage

```java
conversationsController.conversationsUnarchiveAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ConversationsUnarchiveErrorSchemaException) {
        ConversationsUnarchiveErrorSchemaException conversationsUnarchiveErrorSchemaException = (ConversationsUnarchiveErrorSchemaException) cause;
        conversationsUnarchiveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ConversationsUnarchiveErrorSchemaException`](../../doc/models/conversations-unarchive-error-schema-exception.md) |

