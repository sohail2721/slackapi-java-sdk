# Oauth

```java
OauthController oauthController = client.getOauthController();
```

## Class Name

`OauthController`

## Methods

* [Oauth Access](../../doc/controllers/oauth.md#oauth-access)
* [Oauth Token](../../doc/controllers/oauth.md#oauth-token)


# Oauth Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.access](https://api.slack.com/methods/oauth.access)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> oauthAccessAsync(
    final String clientId,
    final String clientSecret,
    final String code,
    final String redirectUri,
    final Boolean singleChannel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `String` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `String` | Query, Optional | Issued when you created your application. |
| `code` | `String` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirectUri` | `String` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `singleChannel` | `Boolean` | Query, Optional | Request the user to add your app only to a single channel. Only valid with a [legacy workspace app](https://api.slack.com/legacy-workspace-apps). |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
oauthController.oauthAccessAsync(null, null, null, null, null).thenAccept(result -> {
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


# Oauth Token

Exchanges a temporary OAuth verifier code for a workspace token.

API method documentation: [https://api.slack.com/methods/oauth.token](https://api.slack.com/methods/oauth.token)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> oauthTokenAsync(
    final String clientId,
    final String clientSecret,
    final String code,
    final String redirectUri,
    final Boolean singleChannel)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `clientId` | `String` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `String` | Query, Optional | Issued when you created your application. |
| `code` | `String` | Query, Optional | The `code` param returned via the OAuth callback. |
| `redirectUri` | `String` | Query, Optional | This must match the originally submitted URI (if one was sent). |
| `singleChannel` | `Boolean` | Query, Optional | Request the user to add your app only to a single channel. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
oauthController.oauthTokenAsync(null, null, null, null, null).thenAccept(result -> {
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

