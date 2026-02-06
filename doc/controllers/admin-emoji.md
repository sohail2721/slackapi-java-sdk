# Admin Emoji

```java
AdminEmojiController adminEmojiController = client.getAdminEmojiController();
```

## Class Name

`AdminEmojiController`

## Methods

* [Admin Emoji Add](../../doc/controllers/admin-emoji.md#admin-emoji-add)
* [Admin Emoji Add Alias](../../doc/controllers/admin-emoji.md#admin-emoji-add-alias)
* [Admin Emoji List](../../doc/controllers/admin-emoji.md#admin-emoji-list)
* [Admin Emoji Remove](../../doc/controllers/admin-emoji.md#admin-emoji-remove)
* [Admin Emoji Rename](../../doc/controllers/admin-emoji.md#admin-emoji-rename)


# Admin Emoji Add

Add an emoji.

API method documentation: [https://api.slack.com/methods/admin.emoji.add](https://api.slack.com/methods/admin.emoji.add)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminEmojiAddAsync(
    final String token,
    final String name,
    final String url)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `String` | Form, Required | The name of the emoji to be removed. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `url` | `String` | Form, Required | The URL of a file to use as an image for the emoji. Square images under 128KB and with transparent backgrounds work best. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String name = "name0";
String url = "url4";

adminEmojiController.adminEmojiAddAsync(token, name, url).thenAccept(result -> {
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


# Admin Emoji Add Alias

Add an emoji alias.

API method documentation: [https://api.slack.com/methods/admin.emoji.addAlias](https://api.slack.com/methods/admin.emoji.addAlias)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminEmojiAddAliasAsync(
    final String token,
    final String name,
    final String aliasFor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `String` | Form, Required | The name of the emoji to be aliased. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `aliasFor` | `String` | Form, Required | The alias of the emoji. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String name = "name0";
String aliasFor = "alias_for4";

adminEmojiController.adminEmojiAddAliasAsync(token, name, aliasFor).thenAccept(result -> {
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


# Admin Emoji List

List emoji for an Enterprise Grid organization.

API method documentation: [https://api.slack.com/methods/admin.emoji.list](https://api.slack.com/methods/admin.emoji.list)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminEmojiListAsync(
    final String token,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `admin.teams:read` |
| `cursor` | `String` | Query, Optional | Set `cursor` to `next_cursor` returned by the previous call to list items in the next page |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Must be between 1 - 1000 both inclusive. |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";

adminEmojiController.adminEmojiListAsync(token, null, null).thenAccept(result -> {
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


# Admin Emoji Remove

Remove an emoji across an Enterprise Grid organization

API method documentation: [https://api.slack.com/methods/admin.emoji.remove](https://api.slack.com/methods/admin.emoji.remove)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminEmojiRemoveAsync(
    final String token,
    final String name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `String` | Form, Required | The name of the emoji to be removed. Colons (`:myemoji:`) around the value are not required, although they may be included. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String name = "name0";

adminEmojiController.adminEmojiRemoveAsync(token, name).thenAccept(result -> {
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


# Admin Emoji Rename

Rename an emoji.

API method documentation: [https://api.slack.com/methods/admin.emoji.rename](https://api.slack.com/methods/admin.emoji.rename)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminEmojiRenameAsync(
    final String token,
    final String name,
    final String newName)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `name` | `String` | Form, Required | The name of the emoji to be renamed. Colons (`:myemoji:`) around the value are not required, although they may be included. |
| `newName` | `String` | Form, Required | The new name of the emoji. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String name = "name0";
String newName = "new_name8";

adminEmojiController.adminEmojiRenameAsync(token, name, newName).thenAccept(result -> {
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

