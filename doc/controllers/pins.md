# Pins

```java
PinsController pinsController = client.getPinsController();
```

## Class Name

`PinsController`

## Methods

* [Pins Add](../../doc/controllers/pins.md#pins-add)
* [Pins List](../../doc/controllers/pins.md#pins-list)
* [Pins Remove](../../doc/controllers/pins.md#pins-remove)


# Pins Add

Pins an item to a channel.

API method documentation: [https://api.slack.com/methods/pins.add](https://api.slack.com/methods/pins.add)

```java
CompletableFuture<ApiResponse<PinsAddSchema>> pinsAddAsync(
    final String token,
    final String channel,
    final String timestamp)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `pins:write` |
| `channel` | `String` | Form, Required | Channel to pin the item in. |
| `timestamp` | `String` | Form, Optional | Timestamp of the message to pin. |

## Requires scope

### slackAuth

`pins:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`PinsAddSchema`](../../doc/models/pins-add-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";

pinsController.pinsAddAsync(token, channel, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof PinsAddErrorSchemaException) {
        PinsAddErrorSchemaException pinsAddErrorSchemaException = (PinsAddErrorSchemaException) cause;
        pinsAddErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`PinsAddErrorSchemaException`](../../doc/models/pins-add-error-schema-exception.md) |


# Pins List

Lists items pinned to a channel.

API method documentation: [https://api.slack.com/methods/pins.list](https://api.slack.com/methods/pins.list)

```java
CompletableFuture<ApiResponse<DynamicResponse>> pinsListAsync(
    final String token,
    final String channel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `pins:read` |
| `channel` | `String` | Query, Required | Channel to get pinned items for. |

## Requires scope

### slackAuth

`pins:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `DynamicResponse`.

## Example Usage

```java
String token = "token6";
String channel = "channel4";

pinsController.pinsListAsync(token, channel).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof PinsListErrorSchemaException) {
        PinsListErrorSchemaException pinsListErrorSchemaException = (PinsListErrorSchemaException) cause;
        pinsListErrorSchemaException.printStackTrace();
    } else {
        // fallback for unexpected errors
        exception.printStackTrace();
    }

    return null;
});
```

## Example Response

```
{
  "items": [
    {
      "channel": "C2U86NC6H",
      "created": 1508881078,
      "created_by": "U2U85N1RZ",
      "message": {
        "permalink": "https://hitchhikers.slack.com/archives/C2U86NC6H/p1508197641000151",
        "pinned_to": [
          "C2U86NC6H"
        ],
        "text": "What is the meaning of life?",
        "ts": "1508197641.000151",
        "type": "message",
        "user": "U2U85N1RZ"
      },
      "type": "message"
    },
    {
      "channel": "C2U86NC6H",
      "created": 1508880991,
      "created_by": "U2U85N1RZ",
      "message": {
        "permalink": "https://hitchhikers.slack.com/archives/C2U86NC6H/p1508284197000015",
        "pinned_to": [
          "C2U86NC6H"
        ],
        "text": "The meaning of life, the universe, and everything is 42.",
        "ts": "1503289197.000015",
        "type": "message",
        "user": "U2U85N1RZ"
      },
      "type": "message"
    }
  ],
  "ok": true
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`PinsListErrorSchemaException`](../../doc/models/pins-list-error-schema-exception.md) |


# Pins Remove

Un-pins an item from a channel.

API method documentation: [https://api.slack.com/methods/pins.remove](https://api.slack.com/methods/pins.remove)

```java
CompletableFuture<ApiResponse<PinsRemoveSchema>> pinsRemoveAsync(
    final String token,
    final String channel,
    final String timestamp)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `pins:write` |
| `channel` | `String` | Form, Required | Channel where the item is pinned to. |
| `timestamp` | `String` | Form, Optional | Timestamp of the message to un-pin. |

## Requires scope

### slackAuth

`pins:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`PinsRemoveSchema`](../../doc/models/pins-remove-schema.md).

## Example Usage

```java
String token = "token6";
String channel = "channel4";

pinsController.pinsRemoveAsync(token, channel, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof PinsRemoveErrorSchemaException) {
        PinsRemoveErrorSchemaException pinsRemoveErrorSchemaException = (PinsRemoveErrorSchemaException) cause;
        pinsRemoveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`PinsRemoveErrorSchemaException`](../../doc/models/pins-remove-error-schema-exception.md) |

