# Files

```java
FilesController filesController = client.getFilesController();
```

## Class Name

`FilesController`

## Methods

* [Files Delete](../../doc/controllers/files.md#files-delete)
* [Files Info](../../doc/controllers/files.md#files-info)
* [Files List](../../doc/controllers/files.md#files-list)
* [Files Revoke Public URL](../../doc/controllers/files.md#files-revoke-public-url)
* [Files Shared Public URL](../../doc/controllers/files.md#files-shared-public-url)
* [Files Upload](../../doc/controllers/files.md#files-upload)


# Files Delete

Deletes a file.

API method documentation: [https://api.slack.com/methods/files.delete](https://api.slack.com/methods/files.delete)

```java
CompletableFuture<ApiResponse<FilesDeleteSchema>> filesDeleteAsync(
    final String token,
    final String file)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `String` | Form, Optional | ID of file to delete. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`FilesDeleteSchema`](../../doc/models/files-delete-schema.md).

## Example Usage

```java
filesController.filesDeleteAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof FilesDeleteErrorSchemaException) {
        FilesDeleteErrorSchemaException filesDeleteErrorSchemaException = (FilesDeleteErrorSchemaException) cause;
        filesDeleteErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`FilesDeleteErrorSchemaException`](../../doc/models/files-delete-error-schema-exception.md) |


# Files Info

Gets information about a file.

API method documentation: [https://api.slack.com/methods/files.info](https://api.slack.com/methods/files.info)

```java
CompletableFuture<ApiResponse<FilesInfoSchema>> filesInfoAsync(
    final String token,
    final String file,
    final String count,
    final String page,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `file` | `String` | Query, Optional | Specify a file by providing its ID. |
| `count` | `String` | Query, Optional | - |
| `page` | `String` | Query, Optional | - |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. |
| `cursor` | `String` | Query, Optional | Parameter for pagination. File comments are paginated for a single file. Set `cursor` equal to the `next_cursor` attribute returned by the previous request's `response_metadata`. This parameter is optional, but pagination is mandatory: the default value simply fetches the first "page" of the collection of comments. See [pagination](/docs/pagination) for more details. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`FilesInfoSchema`](../../doc/models/files-info-schema.md).

## Example Usage

```java
filesController.filesInfoAsync(null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof FilesInfoErrorSchemaException) {
        FilesInfoErrorSchemaException filesInfoErrorSchemaException = (FilesInfoErrorSchemaException) cause;
        filesInfoErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`FilesInfoErrorSchemaException`](../../doc/models/files-info-error-schema-exception.md) |


# Files List

List for a team, in a channel, or from a user with applied filters.

API method documentation: [https://api.slack.com/methods/files.list](https://api.slack.com/methods/files.list)

```java
CompletableFuture<ApiResponse<FilesListSchema>> filesListAsync(
    final String token,
    final String user,
    final String channel,
    final Double tsFrom,
    final Double tsTo,
    final String types,
    final String count,
    final String page,
    final Boolean showFilesHiddenByLimit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `files:read` |
| `user` | `String` | Query, Optional | Filter files created by a single user. |
| `channel` | `String` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `tsFrom` | `Double` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `tsTo` | `Double` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `types` | `String` | Query, Optional | Filter files by type ([see below](#file_types)). You can pass multiple values in the types argument, like `types=spaces,snippets`.The default value is `all`, which does not filter the list. |
| `count` | `String` | Query, Optional | - |
| `page` | `String` | Query, Optional | - |
| `showFilesHiddenByLimit` | `Boolean` | Query, Optional | Show truncated file info for files hidden due to being too old, and the team who owns the file being over the file limit. |

## Requires scope

### slackAuth

`files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`FilesListSchema`](../../doc/models/files-list-schema.md).

## Example Usage

```java
filesController.filesListAsync(null, null, null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof FilesListErrorSchemaException) {
        FilesListErrorSchemaException filesListErrorSchemaException = (FilesListErrorSchemaException) cause;
        filesListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`FilesListErrorSchemaException`](../../doc/models/files-list-error-schema-exception.md) |


# Files Revoke Public URL

Revokes public/external sharing access for a file

API method documentation: [https://api.slack.com/methods/files.revokePublicURL](https://api.slack.com/methods/files.revokePublicURL)

```java
CompletableFuture<ApiResponse<FilesRevokePublicUrlSchema>> filesRevokePublicUrlAsync(
    final String token,
    final String file)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `String` | Form, Optional | File to revoke |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`FilesRevokePublicUrlSchema`](../../doc/models/files-revoke-public-url-schema.md).

## Example Usage

```java
filesController.filesRevokePublicUrlAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof FilesRevokePublicUrlErrorSchemaException) {
        FilesRevokePublicUrlErrorSchemaException filesRevokePublicUrlErrorSchemaException = (FilesRevokePublicUrlErrorSchemaException) cause;
        filesRevokePublicUrlErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`FilesRevokePublicUrlErrorSchemaException`](../../doc/models/files-revoke-public-url-error-schema-exception.md) |


# Files Shared Public URL

Enables a file for public/external sharing.

API method documentation: [https://api.slack.com/methods/files.sharedPublicURL](https://api.slack.com/methods/files.sharedPublicURL)

```java
CompletableFuture<ApiResponse<FilesSharedPublicUrlSchema>> filesSharedPublicUrlAsync(
    final String token,
    final String file)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `String` | Form, Optional | File to share |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`FilesSharedPublicUrlSchema`](../../doc/models/files-shared-public-url-schema.md).

## Example Usage

```java
filesController.filesSharedPublicUrlAsync(null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof FilesSharedPublicUrlErrorSchemaException) {
        FilesSharedPublicUrlErrorSchemaException filesSharedPublicUrlErrorSchemaException = (FilesSharedPublicUrlErrorSchemaException) cause;
        filesSharedPublicUrlErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`FilesSharedPublicUrlErrorSchemaException`](../../doc/models/files-shared-public-url-error-schema-exception.md) |


# Files Upload

Uploads or creates a file.

API method documentation: [https://api.slack.com/methods/files.upload](https://api.slack.com/methods/files.upload)

```java
CompletableFuture<ApiResponse<FilesUploadSchema>> filesUploadAsync(
    final String token,
    final String file,
    final String content,
    final String filetype,
    final String filename,
    final String title,
    final String initialComment,
    final String channels,
    final Double threadTs)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Optional | Authentication token. Requires scope: `files:write:user` |
| `file` | `String` | Form, Optional | File contents via `multipart/form-data`. If omitting this parameter, you must submit `content`. |
| `content` | `String` | Form, Optional | File contents via a POST variable. If omitting this parameter, you must provide a `file`. |
| `filetype` | `String` | Form, Optional | A [file type](/types/file#file_types) identifier. |
| `filename` | `String` | Form, Optional | Filename of file. |
| `title` | `String` | Form, Optional | Title of file. |
| `initialComment` | `String` | Form, Optional | The message text introducing the file in specified `channels`. |
| `channels` | `String` | Form, Optional | Comma-separated list of channel names or IDs where the file will be shared. |
| `threadTs` | `Double` | Form, Optional | Provide another message's `ts` value to upload this file as a reply. Never use a reply's `ts` value; use its parent instead. |

## Requires scope

### slackAuth

`files:write:user`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`FilesUploadSchema`](../../doc/models/files-upload-schema.md).

## Example Usage

```java
filesController.filesUploadAsync(null, null, null, null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof FilesUploadErrorSchemaException) {
        FilesUploadErrorSchemaException filesUploadErrorSchemaException = (FilesUploadErrorSchemaException) cause;
        filesUploadErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`FilesUploadErrorSchemaException`](../../doc/models/files-upload-error-schema-exception.md) |

