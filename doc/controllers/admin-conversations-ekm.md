# Admin Conversations Ekm

```java
AdminConversationsEkmController adminConversationsEkmController = client.getAdminConversationsEkmController();
```

## Class Name

`AdminConversationsEkmController`


# Admin Conversations Ekm List Original Connected Channel Info

List all disconnected channels—i.e., channels that were once connected to other workspaces and then disconnected—and the corresponding original channel IDs for key revocation with EKM.

API method documentation: [https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo](https://api.slack.com/methods/admin.conversations.ekm.listOriginalConnectedChannelInfo)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminConversationsEkmListOriginalConnectedChannelInfoAsync(
    final String token,
    final String channelIds,
    final String teamIds,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin.conversations:read` |
| `channelIds` | `String` | Query, Optional | A comma-separated list of channels to filter to. |
| `teamIds` | `String` | Query, Optional | A comma-separated list of the workspaces to which the channels you would like returned belong. |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page. |

## Requires scope

### slackAuth

`admin.conversations:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

adminConversationsEkmController.adminConversationsEkmListOriginalConnectedChannelInfoAsync(token, null, null, null, null).thenAccept(result -> {
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

