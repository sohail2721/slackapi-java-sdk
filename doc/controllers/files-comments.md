# Files Comments

```java
FilesCommentsController filesCommentsController = client.getFilesCommentsController();
```

## Class Name

`FilesCommentsController`


# Files Comments Delete

Deletes an existing comment on a file.

API method documentation: [https://api.slack.com/methods/files.comments.delete](https://api.slack.com/methods/files.comments.delete)

```java
CompletableFuture<ApiResponse<FilesCommentsDeleteSchema>> filesCommentsDeleteAsync(
    final String token,
    final String file,
    final String id)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `String` | Form, Optional | File to delete a comment from. |
| `id` | `String` | Form, Optional | The comment to delete. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`FilesCommentsDeleteSchema`](../../doc/models/files-comments-delete-schema.md).

## Example Usage

```java
filesCommentsController.filesCommentsDeleteAsync(null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof FilesCommentsDeleteErrorSchemaException) {
        FilesCommentsDeleteErrorSchemaException filesCommentsDeleteErrorSchemaException = (FilesCommentsDeleteErrorSchemaException) cause;
        filesCommentsDeleteErrorSchemaException.printStackTrace();
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
| Default | Standard failure response when used with an invalid token | [`FilesCommentsDeleteErrorSchemaException`](../../doc/models/files-comments-delete-error-schema-exception.md) |

