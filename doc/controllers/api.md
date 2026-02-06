# Api

```java
ApiController apiController = client.getApiController();
```

## Class Name

`ApiController`


# Api Test

Checks API calling code.

API method documentation: [https://api.slack.com/methods/api.test](https://api.slack.com/methods/api.test)

```java
CompletableFuture<ApiResponse<ApiTestSuccessSchema>> apiTestAsync(
    final String error,
    final String foo)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `error` | `String` | Query, Optional | Error response to return |
| `foo` | `String` | Query, Optional | example property to return |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiTestSuccessSchema`](../../doc/models/api-test-success-schema.md).

## Example Usage

```java
apiController.apiTestAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof ApiTestErrorSchemaException) {
        ApiTestErrorSchemaException apiTestErrorSchemaException = (ApiTestErrorSchemaException) cause;
        apiTestErrorSchemaException.printStackTrace();
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
| Default | Artificial error response | [`ApiTestErrorSchemaException`](../../doc/models/api-test-error-schema-exception.md) |

