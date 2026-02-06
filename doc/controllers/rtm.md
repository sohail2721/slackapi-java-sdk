# Rtm

```java
RtmController rtmController = client.getRtmController();
```

## Class Name

`RtmController`


# Rtm Connect

Starts a Real Time Messaging session.

API method documentation: [https://api.slack.com/methods/rtm.connect](https://api.slack.com/methods/rtm.connect)

```java
CompletableFuture<ApiResponse<RtmConnectSchema>> rtmConnectAsync(
    final String token,
    final Boolean batchPresenceAware,
    final Boolean presenceSub)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `rtm:stream` |
| `batchPresenceAware` | `Boolean` | Query, Optional | Batch presence deliveries via subscription. Enabling changes the shape of `presence_change` events. See [batch presence](/docs/presence-and-status#batching). |
| `presenceSub` | `Boolean` | Query, Optional | Only deliver presence events when requested by subscription. See [presence subscriptions](/docs/presence-and-status#subscriptions). |

## Requires scope

### slackAuth

`rtm:stream`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`RtmConnectSchema`](../../doc/models/rtm-connect-schema.md).

## Example Usage

```java
String token = "token6";

rtmController.rtmConnectAsync(token, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof RtmConnectErrorSchemaException) {
        RtmConnectErrorSchemaException rtmConnectErrorSchemaException = (RtmConnectErrorSchemaException) cause;
        rtmConnectErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`RtmConnectErrorSchemaException`](../../doc/models/rtm-connect-error-schema-exception.md) |

