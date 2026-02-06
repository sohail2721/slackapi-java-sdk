# Bots

```java
BotsController botsController = client.getBotsController();
```

## Class Name

`BotsController`


# Bots Info

Gets information about a bot user.

API method documentation: [https://api.slack.com/methods/bots.info](https://api.slack.com/methods/bots.info)

```java
CompletableFuture<ApiResponse<BotsInfoSchema>> botsInfoAsync(
    final String token,
    final String bot)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `users:read` |
| `bot` | `String` | Query, Optional | Bot user to get info on |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`BotsInfoSchema`](../../doc/models/bots-info-schema.md).

## Example Usage

```java
String token = "token6";

botsController.botsInfoAsync(token, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof BotsInfoErrorSchemaException) {
        BotsInfoErrorSchemaException botsInfoErrorSchemaException = (BotsInfoErrorSchemaException) cause;
        botsInfoErrorSchemaException.printStackTrace();
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
| Default | When no bot can be found, it returns an error. | [`BotsInfoErrorSchemaException`](../../doc/models/bots-info-error-schema-exception.md) |

