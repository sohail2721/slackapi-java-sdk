# Auth

```java
AuthController authController = client.getAuthController();
```

## Class Name

`AuthController`

## Methods

* [Auth Revoke](../../doc/controllers/auth.md#auth-revoke)
* [Auth Test](../../doc/controllers/auth.md#auth-test)


# Auth Revoke

Revokes a token.

API method documentation: [https://api.slack.com/methods/auth.revoke](https://api.slack.com/methods/auth.revoke)

```java
CompletableFuture<ApiResponse<AuthRevokeSchema>> authRevokeAsync(
    final String token,
    final Boolean test)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `none` |
| `test` | `Boolean` | Query, Optional | Setting this parameter to `1` triggers a _testing mode_ where the specified token will not actually be revoked. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AuthRevokeSchema`](../../doc/models/auth-revoke-schema.md).

## Example Usage

```java
String token = "token6";

authController.authRevokeAsync(token, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AuthRevokeErrorSchemaException) {
        AuthRevokeErrorSchemaException authRevokeErrorSchemaException = (AuthRevokeErrorSchemaException) cause;
        authRevokeErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AuthRevokeErrorSchemaException`](../../doc/models/auth-revoke-error-schema-exception.md) |


# Auth Test

Checks authentication & identity.

API method documentation: [https://api.slack.com/methods/auth.test](https://api.slack.com/methods/auth.test)

```java
CompletableFuture<ApiResponse<AuthTestSuccessSchema>> authTestAsync(
    final String token)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `none` |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AuthTestSuccessSchema`](../../doc/models/auth-test-success-schema.md).

## Example Usage

```java
String token = "token6";

authController.authTestAsync(token).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AuthTestErrorSchemaException) {
        AuthTestErrorSchemaException authTestErrorSchemaException = (AuthTestErrorSchemaException) cause;
        authTestErrorSchemaException.printStackTrace();
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
| Default | Standard failure response when used with an invalid token | [`AuthTestErrorSchemaException`](../../doc/models/auth-test-error-schema-exception.md) |

