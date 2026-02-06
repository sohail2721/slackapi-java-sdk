# Users

```java
UsersController usersController = client.getUsersController();
```

## Class Name

`UsersController`

## Methods

* [Users Conversations](../../doc/controllers/users.md#users-conversations)
* [Users Delete Photo](../../doc/controllers/users.md#users-delete-photo)
* [Users Get Presence](../../doc/controllers/users.md#users-get-presence)
* [Users Identity](../../doc/controllers/users.md#users-identity)
* [Users Info](../../doc/controllers/users.md#users-info)
* [Users List](../../doc/controllers/users.md#users-list)
* [Users Lookup by Email](../../doc/controllers/users.md#users-lookup-by-email)
* [Users Set Active](../../doc/controllers/users.md#users-set-active)
* [Users Set Photo](../../doc/controllers/users.md#users-set-photo)
* [Users Set Presence](../../doc/controllers/users.md#users-set-presence)


# Users Conversations

List conversations the calling user may access.

API method documentation: [https://api.slack.com/methods/users.conversations](https://api.slack.com/methods/users.conversations)

```java
CompletableFuture<ApiResponse<UsersConversationsSuccessSchema>> usersConversationsAsync(
    final String token,
    final String user,
    final String types,
    final Boolean excludeArchived,
    final Integer limit,
    final String cursor)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `conversations:read` |
| `user` | `String` | Query, Optional | Browse conversations by a specific user ID's membership. Non-public channels are restricted to those where the calling user shares membership. |
| `types` | `String` | Query, Optional | Mix and match channel types by providing a comma-separated list of any combination of `public_channel`, `private_channel`, `mpim`, `im` |
| `excludeArchived` | `Boolean` | Query, Optional | Set to `true` to exclude archived channels from the list |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the list hasn't been reached. Must be an integer no larger than 1000. |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |

## Requires scope

### slackAuth

`channels:read`, `groups:read`, `im:read`, `mpim:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersConversationsSuccessSchema`](../../doc/models/users-conversations-success-schema.md).

## Example Usage

```java
usersController.usersConversationsAsync(null, null, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersConversationsErrorSchemaException) {
        UsersConversationsErrorSchemaException usersConversationsErrorSchemaException = (UsersConversationsErrorSchemaException) cause;
        usersConversationsErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersConversationsErrorSchemaException`](../../doc/models/users-conversations-error-schema-exception.md) |


# Users Delete Photo

Delete the user profile photo

API method documentation: [https://api.slack.com/methods/users.deletePhoto](https://api.slack.com/methods/users.deletePhoto)

```java
CompletableFuture<ApiResponse<UsersDeletePhotoSchema>> usersDeletePhotoAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `users.profile:write` |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersDeletePhotoSchema`](../../doc/models/users-delete-photo-schema.md).

## Example Usage

```java
String token = "token6";

usersController.usersDeletePhotoAsync(token).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersDeletePhotoErrorSchemaException) {
        UsersDeletePhotoErrorSchemaException usersDeletePhotoErrorSchemaException = (UsersDeletePhotoErrorSchemaException) cause;
        usersDeletePhotoErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersDeletePhotoErrorSchemaException`](../../doc/models/users-delete-photo-error-schema-exception.md) |


# Users Get Presence

Gets user presence information.

API method documentation: [https://api.slack.com/methods/users.getPresence](https://api.slack.com/methods/users.getPresence)

```java
CompletableFuture<ApiResponse<ApiMethodUsersGetPresence>> usersGetPresenceAsync(
    final String token,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `users:read` |
| `user` | `String` | Query, Optional | User to get presence info on. Defaults to the authed user. |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`ApiMethodUsersGetPresence`](../../doc/models/api-method-users-get-presence.md).

## Example Usage

```java
String token = "token6";

usersController.usersGetPresenceAsync(token, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersCountsErrorSchemaException) {
        UsersCountsErrorSchemaException usersCountsErrorSchemaException = (UsersCountsErrorSchemaException) cause;
        usersCountsErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersCountsErrorSchemaException`](../../doc/models/users-counts-error-schema-exception.md) |


# Users Identity

Get a user's identity.

API method documentation: [https://api.slack.com/methods/users.identity](https://api.slack.com/methods/users.identity)

```java
CompletableFuture<ApiResponse<DynamicResponse>> usersIdentityAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `identity.basic` |

## Requires scope

### slackAuth

`identity.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type `DynamicResponse`.

## Example Usage

```java
usersController.usersIdentityAsync(null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersIdentityErrorSchemaException) {
        UsersIdentityErrorSchemaException usersIdentityErrorSchemaException = (UsersIdentityErrorSchemaException) cause;
        usersIdentityErrorSchemaException.printStackTrace();
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
  "ok": true,
  "team": {
    "id": "T0G9PQBBK"
  },
  "user": {
    "id": "U0G9QF9C6",
    "name": "Sonny Whether"
  }
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| Default | Typical error response | [`UsersIdentityErrorSchemaException`](../../doc/models/users-identity-error-schema-exception.md) |


# Users Info

Gets information about a user.

API method documentation: [https://api.slack.com/methods/users.info](https://api.slack.com/methods/users.info)

```java
CompletableFuture<ApiResponse<UsersInfoSuccessSchema>> usersInfoAsync(
    final String token,
    final Boolean includeLocale,
    final String user)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `users:read` |
| `includeLocale` | `Boolean` | Query, Optional | Set this to `true` to receive the locale for this user. Defaults to `false` |
| `user` | `String` | Query, Optional | User to get info on |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersInfoSuccessSchema`](../../doc/models/users-info-success-schema.md).

## Example Usage

```java
String token = "token6";

usersController.usersInfoAsync(token, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersInfoErrorSchemaException) {
        UsersInfoErrorSchemaException usersInfoErrorSchemaException = (UsersInfoErrorSchemaException) cause;
        usersInfoErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersInfoErrorSchemaException`](../../doc/models/users-info-error-schema-exception.md) |


# Users List

Lists all users in a Slack team.

API method documentation: [https://api.slack.com/methods/users.list](https://api.slack.com/methods/users.list)

```java
CompletableFuture<ApiResponse<UsersListSchema>> usersListAsync(
    final String token,
    final Integer limit,
    final String cursor,
    final Boolean includeLocale)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Optional | Authentication token. Requires scope: `users:read` |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. Fewer than the requested number of items may be returned, even if the end of the users list hasn't been reached. Providing no `limit` value will result in Slack attempting to deliver you the entire result set. If the collection is too large you may experience `limit_required` or HTTP 500 errors. |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `includeLocale` | `Boolean` | Query, Optional | Set this to `true` to receive the locale for users. Defaults to `false` |

## Requires scope

### slackAuth

`users:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersListSchema`](../../doc/models/users-list-schema.md).

## Example Usage

```java
usersController.usersListAsync(null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersListErrorSchemaException) {
        UsersListErrorSchemaException usersListErrorSchemaException = (UsersListErrorSchemaException) cause;
        usersListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersListErrorSchemaException`](../../doc/models/users-list-error-schema-exception.md) |


# Users Lookup by Email

Find a user with an email address.

API method documentation: [https://api.slack.com/methods/users.lookupByEmail](https://api.slack.com/methods/users.lookupByEmail)

```java
CompletableFuture<ApiResponse<UsersLookupByEmailSuccessSchema>> usersLookupByEmailAsync(
    final String token,
    final String email)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `users:read.email` |
| `email` | `String` | Query, Required | An email address belonging to a user in the workspace |

## Requires scope

### slackAuth

`users:read.email`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersLookupByEmailSuccessSchema`](../../doc/models/users-lookup-by-email-success-schema.md).

## Example Usage

```java
String token = "token6";
String email = "email6";

usersController.usersLookupByEmailAsync(token, email).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersLookupByEmailErrorSchemaException) {
        UsersLookupByEmailErrorSchemaException usersLookupByEmailErrorSchemaException = (UsersLookupByEmailErrorSchemaException) cause;
        usersLookupByEmailErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersLookupByEmailErrorSchemaException`](../../doc/models/users-lookup-by-email-error-schema-exception.md) |


# Users Set Active

Marked a user as active. Deprecated and non-functional.

API method documentation: [https://api.slack.com/methods/users.setActive](https://api.slack.com/methods/users.setActive)

```java
CompletableFuture<ApiResponse<UsersSetActiveSchema>> usersSetActiveAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `users:write` |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersSetActiveSchema`](../../doc/models/users-set-active-schema.md).

## Example Usage

```java
String token = "token6";

usersController.usersSetActiveAsync(token).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersSetActiveErrorSchemaException) {
        UsersSetActiveErrorSchemaException usersSetActiveErrorSchemaException = (UsersSetActiveErrorSchemaException) cause;
        usersSetActiveErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersSetActiveErrorSchemaException`](../../doc/models/users-set-active-error-schema-exception.md) |


# Users Set Photo

Set the user profile photo

API method documentation: [https://api.slack.com/methods/users.setPhoto](https://api.slack.com/methods/users.setPhoto)

```java
CompletableFuture<ApiResponse<UsersSetPhotoSchema>> usersSetPhotoAsync(
    final String token,
    final String cropW,
    final String cropX,
    final String cropY,
    final String image)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `users.profile:write` |
| `cropW` | `String` | Form, Optional | Width/height of crop box (always square) |
| `cropX` | `String` | Form, Optional | X coordinate of top-left corner of crop box |
| `cropY` | `String` | Form, Optional | Y coordinate of top-left corner of crop box |
| `image` | `String` | Form, Optional | File contents via `multipart/form-data`. |

## Requires scope

### slackAuth

`users.profile:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersSetPhotoSchema`](../../doc/models/users-set-photo-schema.md).

## Example Usage

```java
String token = "token6";

usersController.usersSetPhotoAsync(token, null, null, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersSetPhotoErrorSchemaException) {
        UsersSetPhotoErrorSchemaException usersSetPhotoErrorSchemaException = (UsersSetPhotoErrorSchemaException) cause;
        usersSetPhotoErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersSetPhotoErrorSchemaException`](../../doc/models/users-set-photo-error-schema-exception.md) |


# Users Set Presence

Manually sets user presence.

API method documentation: [https://api.slack.com/methods/users.setPresence](https://api.slack.com/methods/users.setPresence)

```java
CompletableFuture<ApiResponse<UsersSetPresenceSchema>> usersSetPresenceAsync(
    final String token,
    final String presence)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `users:write` |
| `presence` | `String` | Form, Required | Either `auto` or `away` |

## Requires scope

### slackAuth

`users:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`UsersSetPresenceSchema`](../../doc/models/users-set-presence-schema.md).

## Example Usage

```java
String token = "token6";
String presence = "presence4";

usersController.usersSetPresenceAsync(token, presence).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof UsersSetPresenceErrorSchemaException) {
        UsersSetPresenceErrorSchemaException usersSetPresenceErrorSchemaException = (UsersSetPresenceErrorSchemaException) cause;
        usersSetPresenceErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`UsersSetPresenceErrorSchemaException`](../../doc/models/users-set-presence-error-schema-exception.md) |

