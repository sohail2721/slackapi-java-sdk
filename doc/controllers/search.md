# Search

```java
SearchController searchController = client.getSearchController();
```

## Class Name

`SearchController`


# Search Messages

Searches for messages matching a query.

API method documentation: [https://api.slack.com/methods/search.messages](https://api.slack.com/methods/search.messages)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> searchMessagesAsync(
    final String token,
    final String query,
    final Integer count,
    final Boolean highlight,
    final Integer page,
    final String sort,
    final String sortDir)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `search:read` |
| `query` | `String` | Query, Required | Search query. |
| `count` | `Integer` | Query, Optional | Pass the number of results you want per "page". Maximum of `100`. |
| `highlight` | `Boolean` | Query, Optional | Pass a value of `true` to enable query highlight markers (see below). |
| `page` | `Integer` | Query, Optional | - |
| `sort` | `String` | Query, Optional | Return matches sorted by either `score` or `timestamp`. |
| `sortDir` | `String` | Query, Optional | Change sort direction to ascending (`asc`) or descending (`desc`). |

## Requires scope

### slackAuth

`search:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String query = "query0";

searchController.searchMessagesAsync(token, query, null, null, null, null, null).thenAccept(result -> {
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

