# Apps Permissions Resources

```java
AppsPermissionsResourcesController appsPermissionsResourcesController = client.getAppsPermissionsResourcesController();
```

## Class Name

`AppsPermissionsResourcesController`


# Apps Permissions Resources List

Returns list of resource grants this app has on a team.

API method documentation: [https://api.slack.com/methods/apps.permissions.resources.list](https://api.slack.com/methods/apps.permissions.resources.list)

```java
CompletableFuture<ApiResponse<AppsPermissionsResourcesListSuccessSchema>> appsPermissionsResourcesListAsync(
    final String token,
    final String cursor,
    final Integer limit)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Query, Required | Authentication token. Requires scope: `none` |
| `cursor` | `String` | Query, Optional | Paginate through collections of data by setting the `cursor` parameter to a `next_cursor` attribute returned by a previous request's `response_metadata`. Default value fetches the first "page" of the collection. See [pagination](/docs/pagination) for more detail. |
| `limit` | `Integer` | Query, Optional | The maximum number of items to return. |

## Requires scope

### slackAuth

`none`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`AppsPermissionsResourcesListSuccessSchema`](../../doc/models/apps-permissions-resources-list-success-schema.md).

## Example Usage

```java
String token = "token6";

appsPermissionsResourcesController.appsPermissionsResourcesListAsync(token, null, null).thenAccept(result -> {
    // TODO success callback handler
    System.out.println(result);
}).exceptionally(exception -> {
    Throwable cause = exception.getCause();

    if (cause instanceof AppsPermissionsResourcesListErrorSchemaException) {
        AppsPermissionsResourcesListErrorSchemaException appsPermissionsResourcesListErrorSchemaException = (AppsPermissionsResourcesListErrorSchemaException) cause;
        appsPermissionsResourcesListErrorSchemaException.printStackTrace();
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
| Default | Typical error response | [`AppsPermissionsResourcesListErrorSchemaException`](../../doc/models/apps-permissions-resources-list-error-schema-exception.md) |

