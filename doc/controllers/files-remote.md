# Files Remote

```java
FilesRemoteController filesRemoteController = client.getFilesRemoteController();
```

## Class Name

`FilesRemoteController`

## Methods

* [Files Remote Add](../../doc/controllers/files-remote.md#files-remote-add)
* [Files Remote Info](../../doc/controllers/files-remote.md#files-remote-info)
* [Files Remote List](../../doc/controllers/files-remote.md#files-remote-list)
* [Files Remote Remove](../../doc/controllers/files-remote.md#files-remote-remove)
* [Files Remote Share](../../doc/controllers/files-remote.md#files-remote-share)
* [Files Remote Update](../../doc/controllers/files-remote.md#files-remote-update)


# Files Remote Add

Adds a file from a remote service

API method documentation: [https://api.slack.com/methods/files.remote.add](https://api.slack.com/methods/files.remote.add)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> filesRemoteAddAsync(
    final String token,
    final String externalId,
    final String title,
    final String filetype,
    final String externalUrl,
    final String previewImage,
    final String indexableFileContents)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `externalId` | `String` | Form, Optional | Creator defined GUID for the file. |
| `title` | `String` | Form, Optional | Title of the file being shared. |
| `filetype` | `String` | Form, Optional | type of file |
| `externalUrl` | `String` | Form, Optional | URL of the remote file. |
| `previewImage` | `String` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexableFileContents` | `String` | Form, Optional | A text file (txt, pdf, doc, etc.) containing textual search terms that are used to improve discovery of the remote file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
filesRemoteController.filesRemoteAddAsync(null, null, null, null, null, null, null).thenAccept(result -> {
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


# Files Remote Info

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.info](https://api.slack.com/methods/files.remote.info)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> filesRemoteInfoAsync(
    final String token,
    final String file,
    final String externalId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `file` | `String` | Query, Optional | Specify a file by providing its ID. |
| `externalId` | `String` | Query, Optional | Creator defined GUID for the file. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
filesRemoteController.filesRemoteInfoAsync(null, null, null).thenAccept(result -> {
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


# Files Remote List

Retrieve information about a remote file added to Slack

API method documentation: [https://api.slack.com/methods/files.remote.list](https://api.slack.com/methods/files.remote.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> filesRemoteListAsync(
    final String token,
    final String channel,
    final Double tsFrom,
    final Double tsTo,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `remote_files:read` |
| `channel` | `String` | Query, Optional | Filter files appearing in a specific channel, indicated by its ID. |
| `tsFrom` | `Double` | Query, Optional | Filter files created after this timestamp (inclusive). |
| `tsTo` | `Double` | Query, Optional | Filter files created before this timestamp (inclusive). |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`remote_files:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
filesRemoteController.filesRemoteListAsync(null, null, null, null, null, null).thenAccept(result -> {
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


# Files Remote Remove

Remove a remote file.

API method documentation: [https://api.slack.com/methods/files.remote.remove](https://api.slack.com/methods/files.remote.remove)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> filesRemoteRemoveAsync(
    final String token,
    final String file,
    final String externalId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `String` | Form, Optional | Specify a file by providing its ID. |
| `externalId` | `String` | Form, Optional | Creator defined GUID for the file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
filesRemoteController.filesRemoteRemoveAsync(null, null, null).thenAccept(result -> {
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


# Files Remote Share

Share a remote file into a channel.

API method documentation: [https://api.slack.com/methods/files.remote.share](https://api.slack.com/methods/files.remote.share)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> filesRemoteShareAsync(
    final String token,
    final String file,
    final String externalId,
    final String channels)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `remote_files:share` |
| `file` | `String` | Query, Optional | Specify a file registered with Slack by providing its ID. Either this field or `external_id` or both are required. |
| `externalId` | `String` | Query, Optional | The globally unique identifier (GUID) for the file, as set by the app registering the file with Slack.  Either this field or `file` or both are required. |
| `channels` | `String` | Query, Optional | Comma-separated list of channel IDs where the file will be shared. |

## Requires scope

### slackAuth

`remote_files:share`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
filesRemoteController.filesRemoteShareAsync(null, null, null, null).thenAccept(result -> {
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


# Files Remote Update

Updates an existing remote file.

API method documentation: [https://api.slack.com/methods/files.remote.update](https://api.slack.com/methods/files.remote.update)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> filesRemoteUpdateAsync(
    final String token,
    final String file,
    final String externalId,
    final String title,
    final String filetype,
    final String externalUrl,
    final String previewImage,
    final String indexableFileContents)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Optional | Authentication token. Requires scope: `remote_files:write` |
| `file` | `String` | Form, Optional | Specify a file by providing its ID. |
| `externalId` | `String` | Form, Optional | Creator defined GUID for the file. |
| `title` | `String` | Form, Optional | Title of the file being shared. |
| `filetype` | `String` | Form, Optional | type of file |
| `externalUrl` | `String` | Form, Optional | URL of the remote file. |
| `previewImage` | `String` | Form, Optional | Preview of the document via `multipart/form-data`. |
| `indexableFileContents` | `String` | Form, Optional | File containing contents that can be used to improve searchability for the remote file. |

## Requires scope

### slackAuth

`remote_files:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
filesRemoteController.filesRemoteUpdateAsync(null, null, null, null, null, null, null, null).thenAccept(result -> {
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

