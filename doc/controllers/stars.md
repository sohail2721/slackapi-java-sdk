# Stars

```java
StarsController starsController = client.getStarsController();
```

## Class Name

`StarsController`

## Methods

* [Stars Add](../../doc/controllers/stars.md#stars-add)
* [Stars List](../../doc/controllers/stars.md#stars-list)
* [Stars Remove](../../doc/controllers/stars.md#stars-remove)


# Stars Add

Adds a star to an item.

API method documentation: [https://api.slack.com/methods/stars.add](https://api.slack.com/methods/stars.add)

```java
CompletableFuture<ApiResponse<StarsAddSchema>> starsAddAsync(
    final String token,
    final String channel,
    final String file,
    final String fileComment,
    final String timestamp)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `String` | Form, Optional | Channel to add star to, or channel where the message to add star to was posted (used with `timestamp`). |
| `file` | `String` | Form, Optional | File to add star to. |
| `fileComment` | `String` | Form, Optional | File comment to add star to. |
| `timestamp` | `String` | Form, Optional | Timestamp of the message to add star to. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`StarsAddSchema`](../../doc/models/stars-add-schema.md).

## Example Usage

```java
String token = "token6";

starsController.starsAddAsync(token, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof StarsAddErrorSchemaException) {
        StarsAddErrorSchemaException starsAddErrorSchemaException = (StarsAddErrorSchemaException) cause;
        starsAddErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`StarsAddErrorSchemaException`](../../doc/models/stars-add-error-schema-exception.md) |


# Stars List

Lists stars for a user.

API method documentation: [https://api.slack.com/methods/stars.list](https://api.slack.com/methods/stars.list)

```java
CompletableFuture<ApiResponse<StarsListSchema>> starsListAsync(
    final String token,
    final String count,
    final String page,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `stars:read` |
| `count` | `String` | Query, Optional | - |
| `page` | `String` | Query, Optional | - |
| `cursor` | `String` | Query, Optional | Parameter for pagination. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection. See [pagination](/docs/pagination) for more details. |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |

## Requires scope

### slackAuth

`stars:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`StarsListSchema`](../../doc/models/stars-list-schema.md).

## Example Usage

```java
starsController.starsListAsync(null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof StarsListErrorSchemaException) {
        StarsListErrorSchemaException starsListErrorSchemaException = (StarsListErrorSchemaException) cause;
        starsListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`StarsListErrorSchemaException`](../../doc/models/stars-list-error-schema-exception.md) |


# Stars Remove

Removes a star from an item.

API method documentation: [https://api.slack.com/methods/stars.remove](https://api.slack.com/methods/stars.remove)

```java
CompletableFuture<ApiResponse<StarsRemoveSchema>> starsRemoveAsync(
    final String token,
    final String channel,
    final String file,
    final String fileComment,
    final String timestamp)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `stars:write` |
| `channel` | `String` | Form, Optional | Channel to remove star from, or channel where the message to remove star from was posted (used with `timestamp`). |
| `file` | `String` | Form, Optional | File to remove star from. |
| `fileComment` | `String` | Form, Optional | File comment to remove star from. |
| `timestamp` | `String` | Form, Optional | Timestamp of the message to remove star from. |

## Requires scope

### slackAuth

`stars:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`StarsRemoveSchema`](../../doc/models/stars-remove-schema.md).

## Example Usage

```java
String token = "token6";

starsController.starsRemoveAsync(token, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof StarsRemoveErrorSchemaException) {
        StarsRemoveErrorSchemaException starsRemoveErrorSchemaException = (StarsRemoveErrorSchemaException) cause;
        starsRemoveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`StarsRemoveErrorSchemaException`](../../doc/models/stars-remove-error-schema-exception.md) |

