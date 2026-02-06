# Chat Scheduled Messages

```java
ChatScheduledMessagesController chatScheduledMessagesController = client.getChatScheduledMessagesController();
```

## Class Name

`ChatScheduledMessagesController`


# Chat Scheduled Messages List

Returns a list of scheduled messages.

API method documentation: [https://api.slack.com/methods/chat.scheduledMessages.list](https://api.slack.com/methods/chat.scheduledMessages.list)

```java
CompletableFuture<ApiResponse<ChatScheduledMessagesListSchema>> chatScheduledMessagesListAsync(
    final String token,
    final String channel,
    final Double latest,
    final Double oldest,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `none` |
| `channel` | `String` | Query, Optional | The channel of the scheduled messages |
| `latest` | `Double` | Query, Optional | A UNIX timestamp of the latest value in the time range |
| `oldest` | `Double` | Query, Optional | A UNIX timestamp of the oldest value in the time range |
| `limit` | `Integer` | Query, Optional | Maximum number of original entries to return. |
| `cursor` | `String` | Query, Optional | For pagination purposes, this is the `cursor` value returned from a previous call to `chat.scheduledmessages.list` indicating where you want to start this call from. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ChatScheduledMessagesListSchema`](../../doc/models/chat-scheduled-messages-list-schema.md).

## Example Usage

```java
chatScheduledMessagesController.chatScheduledMessagesListAsync(null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ChatScheduledMessagesListErrorSchemaException) {
        ChatScheduledMessagesListErrorSchemaException chatScheduledMessagesListErrorSchemaException = (ChatScheduledMessagesListErrorSchemaException) cause;
        chatScheduledMessagesListErrorSchemaException.printStackTrace();
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
| Default | Typical error response if the channel passed is invalid | [`ChatScheduledMessagesListErrorSchemaException`](../../doc/models/chat-scheduled-messages-list-error-schema-exception.md) |

