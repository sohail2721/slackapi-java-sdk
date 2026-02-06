# Chat

```java
ChatController chatController = client.getChatController();
```

## Class Name

`ChatController`

## Methods

* [Chat Delete](../../doc/controllers/chat.md#chat-delete)
* [Chat Delete Scheduled Message](../../doc/controllers/chat.md#chat-delete-scheduled-message)
* [Chat Get Permalink](../../doc/controllers/chat.md#chat-get-permalink)
* [Chat Me Message](../../doc/controllers/chat.md#chat-me-message)
* [Chat Post Ephemeral](../../doc/controllers/chat.md#chat-post-ephemeral)
* [Chat Post Message](../../doc/controllers/chat.md#chat-post-message)
* [Chat Schedule Message](../../doc/controllers/chat.md#chat-schedule-message)
* [Chat Unfurl](../../doc/controllers/chat.md#chat-unfurl)
* [Chat Update](../../doc/controllers/chat.md#chat-update)


# Chat Delete

Deletes a message.

API method documentation: [https://api.slack.com/methods/chat.delete](https://api.slack.com/methods/chat.delete)

```java
CompletableFuture<ApiResponse<ChatDeleteSuccessSchema>> chatDeleteAsync(
    final String token,
    final Double ts,
    final String channel,
    final Boolean asUser)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `ts` | `Double` | Form, Optional | Timestamp of the message to be deleted. |
| `channel` | `String` | Form, Optional | Channel containing the message to be deleted. |
| `asUser` | `Boolean` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatDeleteSuccessSchema`](../../doc/models/chat-delete-success-schema.md).

## Example Usage

```java
chatController.chatDeleteAsync(null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatDeleteErrorSchemaException) {
        ChatDeleteErrorSchemaException chatDeleteErrorSchemaException = (ChatDeleteErrorSchemaException) cause;
        chatDeleteErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ChatDeleteErrorSchemaException`](../../doc/models/chat-delete-error-schema-exception.md) |


# Chat Delete Scheduled Message

Deletes a pending scheduled message from the queue.

API method documentation: [https://api.slack.com/methods/chat.deleteScheduledMessage](https://api.slack.com/methods/chat.deleteScheduledMessage)

```java
CompletableFuture<ApiResponse<ChatDeleteScheduledMessageSchema>> chatDeleteScheduledMessageAsync(
    final String token,
    final String channel,
    final String scheduledMessageId,
    final Boolean asUser)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `String` | Form, Required | The channel the scheduled_message is posting to |
| `scheduledMessageId` | `String` | Form, Required | `scheduled_message_id` returned from call to chat.scheduleMessage |
| `asUser` | `Boolean` | Form, Optional | Pass true to delete the message as the authed user with `chat:write:user` scope. [Bot users](/bot-users) in this context are considered authed users. If unused or false, the message will be deleted with `chat:write:bot` scope. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatDeleteScheduledMessageSchema`](../../doc/models/chat-delete-scheduled-message-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";
String scheduledMessageId = "scheduled_message_id8";

chatController.chatDeleteScheduledMessageAsync(token, channel, scheduledMessageId, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatDeleteScheduledMessageErrorSchemaException) {
        ChatDeleteScheduledMessageErrorSchemaException chatDeleteScheduledMessageErrorSchemaException = (ChatDeleteScheduledMessageErrorSchemaException) cause;
        chatDeleteScheduledMessageErrorSchemaException.printStackTrace();
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
| Default | Typical error response if no message is found | [`ChatDeleteScheduledMessageErrorSchemaException`](../../doc/models/chat-delete-scheduled-message-error-schema-exception.md) |


# Chat Get Permalink

Retrieve a permalink URL for a specific extant message

API method documentation: [https://api.slack.com/methods/chat.getPermalink](https://api.slack.com/methods/chat.getPermalink)

```java
CompletableFuture<ApiResponse<ChatGetPermalinkSuccessSchema>> chatGetPermalinkAsync(
    final String token,
    final String channel,
    final String messageTs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `none` |
| `channel` | `String` | Query, Required | The ID of the conversation or channel containing the message |
| `messageTs` | `String` | Query, Required | A message's `ts` value, uniquely identifying it within a channel |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatGetPermalinkSuccessSchema`](../../doc/models/chat-get-permalink-success-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";
String messageTs = "message_ts4";

chatController.chatGetPermalinkAsync(token, channel, messageTs).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatGetPermalinkErrorSchemaException) {
        ChatGetPermalinkErrorSchemaException chatGetPermalinkErrorSchemaException = (ChatGetPermalinkErrorSchemaException) cause;
        chatGetPermalinkErrorSchemaException.printStackTrace();
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
| Default | Error response when channel cannot be found | [`ChatGetPermalinkErrorSchemaException`](../../doc/models/chat-get-permalink-error-schema-exception.md) |


# Chat Me Message

Share a me message into a channel.

API method documentation: [https://api.slack.com/methods/chat.meMessage](https://api.slack.com/methods/chat.meMessage)

```java
CompletableFuture<ApiResponse<ChatMeMessageSchema>> chatMeMessageAsync(
    final String token,
    final String channel,
    final String text)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `String` | Form, Optional | Channel to send message to. Can be a public channel, private group or IM channel. Can be an encoded ID, or a name. |
| `text` | `String` | Form, Optional | Text of the message to send. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatMeMessageSchema`](../../doc/models/chat-me-message-schema.md).

## Example Usage

```java
chatController.chatMeMessageAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatMeMessageErrorSchemaException) {
        ChatMeMessageErrorSchemaException chatMeMessageErrorSchemaException = (ChatMeMessageErrorSchemaException) cause;
        chatMeMessageErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ChatMeMessageErrorSchemaException`](../../doc/models/chat-me-message-error-schema-exception.md) |


# Chat Post Ephemeral

Sends an ephemeral message to a user in a channel.

API method documentation: [https://api.slack.com/methods/chat.postEphemeral](https://api.slack.com/methods/chat.postEphemeral)

```java
CompletableFuture<ApiResponse<ChatPostEphemeralSuccessSchema>> chatPostEphemeralAsync(
    final String token,
    final String channel,
    final String user,
    final Boolean asUser,
    final String attachments,
    final String blocks,
    final String iconEmoji,
    final String iconUrl,
    final Boolean linkNames,
    final String parse,
    final String text,
    final String threadTs,
    final String username)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `String` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. |
| `user` | `String` | Form, Required | `id` of the user who will receive the ephemeral message. The user should be in the channel specified by the `channel` argument. |
| `asUser` | `Boolean` | Form, Optional | Pass true to post the message as the authed user. Defaults to true if the chat:write:bot scope is not included. Otherwise, defaults to false. |
| `attachments` | `String` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `String` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `iconEmoji` | `String` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `iconUrl` | `String` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `linkNames` | `Boolean` | Form, Optional | Find and link channel names and usernames. |
| `parse` | `String` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `text` | `String` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `threadTs` | `String` | Form, Optional | Provide another message's `ts` value to post this message in a thread. Avoid using a reply's `ts` value; use its parent's value instead. Ephemeral messages in threads are only shown if there is already an active thread. |
| `username` | `String` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatPostEphemeralSuccessSchema`](../../doc/models/chat-post-ephemeral-success-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";
String user = "user0";

chatController.chatPostEphemeralAsync(token, channel, user, null, null, null, null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatPostEphemeralErrorSchemaException) {
        ChatPostEphemeralErrorSchemaException chatPostEphemeralErrorSchemaException = (ChatPostEphemeralErrorSchemaException) cause;
        chatPostEphemeralErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ChatPostEphemeralErrorSchemaException`](../../doc/models/chat-post-ephemeral-error-schema-exception.md) |


# Chat Post Message

Sends a message to a channel.

API method documentation: [https://api.slack.com/methods/chat.postMessage](https://api.slack.com/methods/chat.postMessage)

```java
CompletableFuture<ApiResponse<ChatPostMessageSuccessSchema>> chatPostMessageAsync(
    final String token,
    final String channel,
    final String asUser,
    final String attachments,
    final String blocks,
    final String iconEmoji,
    final String iconUrl,
    final Boolean linkNames,
    final Boolean mrkdwn,
    final String parse,
    final Boolean replyBroadcast,
    final String text,
    final String threadTs,
    final Boolean unfurlLinks,
    final Boolean unfurlMedia,
    final String username)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `String` | Form, Required | Channel, private group, or IM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `asUser` | `String` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [authorship](#authorship) below. |
| `attachments` | `String` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `String` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `iconEmoji` | `String` | Form, Optional | Emoji to use as the icon for this message. Overrides `icon_url`. Must be used in conjunction with `as_user` set to `false`, otherwise ignored. See [authorship](#authorship) below. |
| `iconUrl` | `String` | Form, Optional | URL to an image to use as the icon for this message. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |
| `linkNames` | `Boolean` | Form, Optional | Find and link channel names and usernames. |
| `mrkdwn` | `Boolean` | Form, Optional | Disable Slack markup parsing by setting to `false`. Enabled by default. |
| `parse` | `String` | Form, Optional | Change how messages are treated. Defaults to `none`. See [below](#formatting). |
| `replyBroadcast` | `Boolean` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |
| `text` | `String` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `threadTs` | `String` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `unfurlLinks` | `Boolean` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurlMedia` | `Boolean` | Form, Optional | Pass false to disable unfurling of media content. |
| `username` | `String` | Form, Optional | Set your bot's user name. Must be used in conjunction with `as_user` set to false, otherwise ignored. See [authorship](#authorship) below. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatPostMessageSuccessSchema`](../../doc/models/chat-post-message-success-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";

chatController.chatPostMessageAsync(token, channel, null, null, null, null, null, null, null, null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatPostMessageErrorSchemaException) {
        ChatPostMessageErrorSchemaException chatPostMessageErrorSchemaException = (ChatPostMessageErrorSchemaException) cause;
        chatPostMessageErrorSchemaException.printStackTrace();
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
| Default | Typical error response if too many attachments are included | [`ChatPostMessageErrorSchemaException`](../../doc/models/chat-post-message-error-schema-exception.md) |


# Chat Schedule Message

Schedules a message to be sent to a channel.

API method documentation: [https://api.slack.com/methods/chat.scheduleMessage](https://api.slack.com/methods/chat.scheduleMessage)

```java
CompletableFuture<ApiResponse<ChatScheduleMessageSuccessSchema>> chatScheduleMessageAsync(
    final String token,
    final String channel,
    final String text,
    final String postAt,
    final String parse,
    final Boolean asUser,
    final Boolean linkNames,
    final String attachments,
    final String blocks,
    final Boolean unfurlLinks,
    final Boolean unfurlMedia,
    final Double threadTs,
    final Boolean replyBroadcast)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `chat:write` |
| `channel` | `String` | Form, Optional | Channel, private group, or DM channel to send message to. Can be an encoded ID, or a name. See [below](#channels) for more details. |
| `text` | `String` | Form, Optional | How this field works and whether it is required depends on other fields you use in your API call. [See below](#text_usage) for more detail. |
| `postAt` | `String` | Form, Optional | Unix EPOCH timestamp of time in future to send the message. |
| `parse` | `String` | Form, Optional | Change how messages are treated. Defaults to `none`. See [chat.postMessage](chat.postMessage#formatting). |
| `asUser` | `Boolean` | Form, Optional | Pass true to post the message as the authed user, instead of as a bot. Defaults to false. See [chat.postMessage](chat.postMessage#authorship). |
| `linkNames` | `Boolean` | Form, Optional | Find and link channel names and usernames. |
| `attachments` | `String` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. |
| `blocks` | `String` | Form, Optional | A JSON-based array of structured blocks, presented as a URL-encoded string. |
| `unfurlLinks` | `Boolean` | Form, Optional | Pass true to enable unfurling of primarily text-based content. |
| `unfurlMedia` | `Boolean` | Form, Optional | Pass false to disable unfurling of media content. |
| `threadTs` | `Double` | Form, Optional | Provide another message's `ts` value to make this message a reply. Avoid using a reply's `ts` value; use its parent instead. |
| `replyBroadcast` | `Boolean` | Form, Optional | Used in conjunction with `thread_ts` and indicates whether reply should be made visible to everyone in the channel or conversation. Defaults to `false`. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatScheduleMessageSuccessSchema`](../../doc/models/chat-schedule-message-success-schema.md).

## Example Usage

```java
chatController.chatScheduleMessageAsync(null, null, null, null, null, null, null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatScheduleMessageErrorSchemaException) {
        ChatScheduleMessageErrorSchemaException chatScheduleMessageErrorSchemaException = (ChatScheduleMessageErrorSchemaException) cause;
        chatScheduleMessageErrorSchemaException.printStackTrace();
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
| Default | Typical error response if the `post_at` is invalid (ex. in the past or too far into the future) | [`ChatScheduleMessageErrorSchemaException`](../../doc/models/chat-schedule-message-error-schema-exception.md) |


# Chat Unfurl

Provide custom unfurl behavior for user-posted URLs

API method documentation: [https://api.slack.com/methods/chat.unfurl](https://api.slack.com/methods/chat.unfurl)

```java
CompletableFuture<ApiResponse<ChatUnfurlSuccessSchema>> chatUnfurlAsync(
    final String token,
    final String channel,
    final String ts,
    final String unfurls,
    final String userAuthMessage,
    final Boolean userAuthRequired,
    final String userAuthUrl)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `links:write` |
| `channel` | `String` | Form, Required | Channel ID of the message |
| `ts` | `String` | Form, Required | Timestamp of the message to add unfurl behavior to. |
| `unfurls` | `String` | Form, Optional | URL-encoded JSON map with keys set to URLs featured in the the message, pointing to their unfurl blocks or message attachments. |
| `userAuthMessage` | `String` | Form, Optional | Provide a simply-formatted string to send as an ephemeral message to the user as invitation to authenticate further and enable full unfurling behavior |
| `userAuthRequired` | `Boolean` | Form, Optional | Set to `true` or `1` to indicate the user must install your Slack app to trigger unfurls for this domain |
| `userAuthUrl` | `String` | Form, Optional | Send users to this custom URL where they will complete authentication in your app to fully trigger unfurling. Value should be properly URL-encoded. |

## Requires scope

### slackAuth

`links:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatUnfurlSuccessSchema`](../../doc/models/chat-unfurl-success-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";
String ts = "ts2";

chatController.chatUnfurlAsync(token, channel, ts, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatUnfurlErrorSchemaException) {
        ChatUnfurlErrorSchemaException chatUnfurlErrorSchemaException = (ChatUnfurlErrorSchemaException) cause;
        chatUnfurlErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ChatUnfurlErrorSchemaException`](../../doc/models/chat-unfurl-error-schema-exception.md) |


# Chat Update

Updates a message.

API method documentation: [https://api.slack.com/methods/chat.update](https://api.slack.com/methods/chat.update)

```java
CompletableFuture<ApiResponse<ChatUpdateSuccessSchema>> chatUpdateAsync(
    final String token,
    final String channel,
    final String ts,
    final String asUser,
    final String attachments,
    final String blocks,
    final String linkNames,
    final String parse,
    final String text)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `chat:write` |
| `channel` | `String` | Form, Required | Channel containing the message to be updated. |
| `ts` | `String` | Form, Required | Timestamp of the message to be updated. |
| `asUser` | `String` | Form, Optional | Pass true to update the message as the authed user. [Bot users](/bot-users) in this context are considered authed users. |
| `attachments` | `String` | Form, Optional | A JSON-based array of structured attachments, presented as a URL-encoded string. This field is required when not presenting `text`. If you don't include this field, the message's previous `attachments` will be retained. To remove previous `attachments`, include an empty array for this field. |
| `blocks` | `String` | Form, Optional | A JSON-based array of [structured blocks](/block-kit/building), presented as a URL-encoded string. If you don't include this field, the message's previous `blocks` will be retained. To remove previous `blocks`, include an empty array for this field. |
| `linkNames` | `String` | Form, Optional | Find and link channel names and usernames. Defaults to `none`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `none`. |
| `parse` | `String` | Form, Optional | Change how messages are treated. Defaults to `client`, unlike `chat.postMessage`. Accepts either `none` or `full`. If you do not specify a value for this field, the original value set for the message will be overwritten with the default, `client`. |
| `text` | `String` | Form, Optional | New text for the message, using the [default formatting rules](/reference/surfaces/formatting). It's not required when presenting `blocks` or `attachments`. |

## Requires scope

### slackAuth

`chat:write:bot`, `chat:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatUpdateSuccessSchema`](../../doc/models/chat-update-success-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";
String ts = "ts2";

chatController.chatUpdateAsync(token, channel, ts, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatUpdateErrorSchemaException) {
        ChatUpdateErrorSchemaException chatUpdateErrorSchemaException = (ChatUpdateErrorSchemaException) cause;
        chatUpdateErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ChatUpdateErrorSchemaException`](../../doc/models/chat-update-error-schema-exception.md) |

