# Oauth V 2

```java
OauthV2Controller oauthV2Controller = client.getOauthV2Controller();
```

## Class Name

`OauthV2Controller`


# Oauth V 2 Access

Exchanges a temporary OAuth verifier code for an access token.

API method documentation: [https://api.slack.com/methods/oauth.v2.access](https://api.slack.com/methods/oauth.v2.access)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> oauthV2AccessAsync(
    final String code,
    final String clientId,
    final String clientSecret,
    final String redirectUri)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `code` | `String` | Query, Required | The `code` param returned via the OAuth callback. |
| `clientId` | `String` | Query, Optional | Issued when you created your application. |
| `clientSecret` | `String` | Query, Optional | Issued when you created your application. |
| `redirectUri` | `String` | Query, Optional | This must match the originally submitted URI (if one was sent). |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String code = "code8";

oauthV2Controller.oauthV2AccessAsync(code, null, null, null).thenAccept(result -> {
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

