# Reactions

```java
ReactionsController reactionsController = client.getReactionsController();
```

## Class Name

`ReactionsController`

## Methods

* [Reactions Add](../../doc/controllers/reactions.md#reactions-add)
* [Reactions Get](../../doc/controllers/reactions.md#reactions-get)
* [Reactions List](../../doc/controllers/reactions.md#reactions-list)
* [Reactions Remove](../../doc/controllers/reactions.md#reactions-remove)


# Reactions Add

Adds a reaction to an item.

API method documentation: [https://api.slack.com/methods/reactions.add](https://api.slack.com/methods/reactions.add)

```java
CompletableFuture<ApiResponse<ReactionsAddSchema>> reactionsAddAsync(
    final String channel,
    final String name,
    final String timestamp,
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `channel` | `String` | Form, Required | Channel where the message to add reaction to was posted. |
| `name` | `String` | Form, Required | Reaction (emoji) name. |
| `timestamp` | `String` | Form, Required | Timestamp of the message to add reaction to. |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `reactions:write` |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ReactionsAddSchema`](../../doc/models/reactions-add-schema.md).

## Example Usage

```java
String channel = "channel4";
String name = "name0";
String timestamp = "timestamp2";
String token = "token6";

reactionsController.reactionsAddAsync(channel, name, timestamp, token).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ReactionsAddErrorSchemaException) {
        ReactionsAddErrorSchemaException reactionsAddErrorSchemaException = (ReactionsAddErrorSchemaException) cause;
        reactionsAddErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ReactionsAddErrorSchemaException`](../../doc/models/reactions-add-error-schema-exception.md) |


# Reactions Get

Gets reactions for an item.

API method documentation: [https://api.slack.com/methods/reactions.get](https://api.slack.com/methods/reactions.get)

```java
CompletableFuture<ApiResponse<Object>> reactionsGetAsync(
    final String token,
    final String channel,
    final String file,
    final String fileComment,
    final Boolean full,
    final String timestamp)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `channel` | `String` | Query, Optional | Channel where the message to get reactions for was posted. |
| `file` | `String` | Query, Optional | File to get reactions for. |
| `fileComment` | `String` | Query, Optional | File comment to get reactions for. |
| `full` | `Boolean` | Query, Optional | If true always return the complete reaction list. |
| `timestamp` | `String` | Query, Optional | Timestamp of the message to get reactions for. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `Object`.

## Example Usage

```java
String token = "token6";

reactionsController.reactionsGetAsync(token, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ReactionsGetErrorSchemaException) {
        ReactionsGetErrorSchemaException reactionsGetErrorSchemaException = (ReactionsGetErrorSchemaException) cause;
        reactionsGetErrorSchemaException.printStackTrace();
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
  "file": {
    "channels": [
      "C2U7V2YA2"
    ],
    "comments_count": 1,
    "created": 1507850315,
    "groups": [],
    "id": "F7H0D7ZA4",
    "ims": [],
    "name": "computer.gif",
    "reactions": [
      {
        "count": 1,
        "name": "stuck_out_tongue_winking_eye",
        "users": [
          "U2U85N1RV"
        ]
      }
    ],
    "timestamp": 1507850315,
    "title": "computer.gif",
    "user": "U2U85N1RV"
  },
  "ok": true,
  "type": "file"
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`ReactionsGetErrorSchemaException`](../../doc/models/reactions-get-error-schema-exception.md) |


# Reactions List

Lists reactions made by a user.

API method documentation: [https://api.slack.com/methods/reactions.list](https://api.slack.com/methods/reactions.list)

```java
CompletableFuture<ApiResponse<ReactionsListSchema>> reactionsListAsync(
    final String token,
    final String user,
    final Boolean full,
    final Integer count,
    final Integer page,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `reactions:read` |
| `user` | `String` | Query, Optional | Show reactions made by this user. Defaults to the authed user. |
| `full` | `Boolean` | Query, Optional | If true always return the complete reaction list. |
| `count` | `Integer` | Query, Optional | - |
| `page` | `Integer` | Query, Optional | - |
| `cursor` | `String` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. See [pagination](/docs/pagination) for more details. |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |

## Requires scope

### slackAuth

`reactions:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ReactionsListSchema`](../../doc/models/reactions-list-schema.md).

## Example Usage

```java
String token = "token6";

reactionsController.reactionsListAsync(token, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ReactionsListErrorSchemaException) {
        ReactionsListErrorSchemaException reactionsListErrorSchemaException = (ReactionsListErrorSchemaException) cause;
        reactionsListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ReactionsListErrorSchemaException`](../../doc/models/reactions-list-error-schema-exception.md) |


# Reactions Remove

Removes a reaction from an item.

API method documentation: [https://api.slack.com/methods/reactions.remove](https://api.slack.com/methods/reactions.remove)

```java
CompletableFuture<ApiResponse<ReactionsRemoveSchema>> reactionsRemoveAsync(
    final String token,
    final String name,
    final String file,
    final String fileComment,
    final String channel,
    final String timestamp)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `reactions:write` |
| `name` | `String` | Form, Required | Reaction (emoji) name. |
| `file` | `String` | Form, Optional | File to remove reaction from. |
| `fileComment` | `String` | Form, Optional | File comment to remove reaction from. |
| `channel` | `String` | Form, Optional | Channel where the message to remove reaction from was posted. |
| `timestamp` | `String` | Form, Optional | Timestamp of the message to remove reaction from. |

## Requires scope

### slackAuth

`reactions:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ReactionsRemoveSchema`](../../doc/models/reactions-remove-schema.md).

## Example Usage

```java
String token = "token6";
String name = "name0";

reactionsController.reactionsRemoveAsync(token, name, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ReactionsRemoveErrorSchemaException) {
        ReactionsRemoveErrorSchemaException reactionsRemoveErrorSchemaException = (ReactionsRemoveErrorSchemaException) cause;
        reactionsRemoveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`ReactionsRemoveErrorSchemaException`](../../doc/models/reactions-remove-error-schema-exception.md) |

