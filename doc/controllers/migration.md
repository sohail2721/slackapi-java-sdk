# Migration

```java
MigrationController migrationController = client.getMigrationController();
```

## Class Name

`MigrationController`


# Migration Exchange

For Enterprise Grid workspaces, map local user IDs to global user IDs

API method documentation: [https://api.slack.com/methods/migration.exchange](https://api.slack.com/methods/migration.exchange)

```java
CompletableFuture<ApiResponse<MigrationExchangeSuccessSchema>> migrationExchangeAsync(
    final String token,
    final String users,
    final String teamId,
    final Boolean toOld)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `tokens.basic` |
| `users` | `String` | Query, Required | A comma-separated list of user ids, up to 400 per request |
| `teamId` | `String` | Query, Optional | Specify team_id starts with `T` in case of Org Token |
| `toOld` | `Boolean` | Query, Optional | Specify `true` to convert `W` global user IDs to workspace-specific `U` IDs. Defaults to `false`. |

## Requires scope

### slackAuth

`tokens.basic`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`MigrationExchangeSuccessSchema`](../../doc/models/migration-exchange-success-schema.md).

## Example Usage

```java
String token = "token6";
String users = "users6";

migrationController.migrationExchangeAsync(token, users, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof MigrationExchangeErrorSchemaException) {
        MigrationExchangeErrorSchemaException migrationExchangeErrorSchemaException = (MigrationExchangeErrorSchemaException) cause;
        migrationExchangeErrorSchemaException.printStackTrace();
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
| Default | Typical error response when there are no mappings to provide | [`MigrationExchangeErrorSchemaException`](../../doc/models/migration-exchange-error-schema-exception.md) |

