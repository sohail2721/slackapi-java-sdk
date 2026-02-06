# Dialog

```java
DialogController dialogController = client.getDialogController();
```

## Class Name

`DialogController`


# Dialog Open

Open a dialog with a user

API method documentation: [https://api.slack.com/methods/dialog.open](https://api.slack.com/methods/dialog.open)

```java
CompletableFuture<ApiResponse<DialogOpenSchema>> dialogOpenAsync(
    final String token,
    final String dialog,
    final String triggerId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `none` |
| `dialog` | `String` | Query, Required | The dialog definition. This must be a JSON-encoded string. |
| `triggerId` | `String` | Query, Required | Exchange a trigger to post to the user. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DialogOpenSchema`](../../doc/models/dialog-open-schema.md).

## Example Usage

```java
String token = "token6";
String dialog = "dialog4";
String triggerId = "trigger_id6";

dialogController.dialogOpenAsync(token, dialog, triggerId).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof DialogOpenErrorSchemaException) {
        DialogOpenErrorSchemaException dialogOpenErrorSchemaException = (DialogOpenErrorSchemaException) cause;
        dialogOpenErrorSchemaException.printStackTrace();
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
| Default | Typical error response, before getting to any possible validation errors. | [`DialogOpenErrorSchemaException`](../../doc/models/dialog-open-error-schema-exception.md) |

