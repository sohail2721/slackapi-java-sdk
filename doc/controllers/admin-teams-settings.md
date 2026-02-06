# Admin Teams Settings

```java
AdminTeamsSettingsController adminTeamsSettingsController = client.getAdminTeamsSettingsController();
```

## Class Name

`AdminTeamsSettingsController`

## Methods

* [Admin Teams Settings Info](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-info)
* [Admin Teams Settings Set Default Channels](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-default-channels)
* [Admin Teams Settings Set Description](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-description)
* [Admin Teams Settings Set Discoverability](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-discoverability)
* [Admin Teams Settings Set Icon](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-icon)
* [Admin Teams Settings Set Name](../../doc/controllers/admin-teams-settings.md#admin-teams-settings-set-name)


# Admin Teams Settings Info

Fetch information about settings in a workspace

API method documentation: [https://api.slack.com/methods/admin.teams.settings.info](https://api.slack.com/methods/admin.teams.settings.info)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsSettingsInfoAsync(
    final String token,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.teams:read` |
| `teamId` | `String` | Query, Required | - |

## Requires scope

### slackAuth

`admin.teams:read`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";

adminTeamsSettingsController.adminTeamsSettingsInfoAsync(token, teamId).thenAccept(result -> {
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


# Admin Teams Settings Set Default Channels

Set the default channels of a workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDefaultChannels](https://api.slack.com/methods/admin.teams.settings.setDefaultChannels)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsSettingsSetDefaultChannelsAsync(
    final String token,
    final String teamId,
    final String channelIds)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `String` | Form, Required | ID for the workspace to set the default channel for. |
| `channelIds` | `String` | Form, Required | An array of channel IDs. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String channelIds = "channel_ids8";

adminTeamsSettingsController.adminTeamsSettingsSetDefaultChannelsAsync(token, teamId, channelIds).thenAccept(result -> {
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


# Admin Teams Settings Set Description

Set the description of a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDescription](https://api.slack.com/methods/admin.teams.settings.setDescription)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsSettingsSetDescriptionAsync(
    final String token,
    final String teamId,
    final String description)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `String` | Form, Required | ID for the workspace to set the description for. |
| `description` | `String` | Form, Required | The new description for the workspace. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String description = "description0";

adminTeamsSettingsController.adminTeamsSettingsSetDescriptionAsync(token, teamId, description).thenAccept(result -> {
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


# Admin Teams Settings Set Discoverability

An API method that allows admins to set the discoverability of a given workspace

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setDiscoverability](https://api.slack.com/methods/admin.teams.settings.setDiscoverability)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsSettingsSetDiscoverabilityAsync(
    final String token,
    final String teamId,
    final String discoverability)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `String` | Form, Required | The ID of the workspace to set discoverability on. |
| `discoverability` | `String` | Form, Required | This workspace's discovery setting. It must be set to one of `open`, `invite_only`, `closed`, or `unlisted`. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String discoverability = "discoverability0";

adminTeamsSettingsController.adminTeamsSettingsSetDiscoverabilityAsync(token, teamId, discoverability).thenAccept(result -> {
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


# Admin Teams Settings Set Icon

Sets the icon of a workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setIcon](https://api.slack.com/methods/admin.teams.settings.setIcon)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsSettingsSetIconAsync(
    final String token,
    final String imageUrl,
    final String teamId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Form, Required | Authentication token. Requires scope: `admin.teams:write` |
| `imageUrl` | `String` | Form, Required | Image URL for the icon |
| `teamId` | `String` | Form, Required | ID for the workspace to set the icon for. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String imageUrl = "image_url6";
String teamId = "team_id6";

adminTeamsSettingsController.adminTeamsSettingsSetIconAsync(token, imageUrl, teamId).thenAccept(result -> {
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


# Admin Teams Settings Set Name

Set the name of a given workspace.

API method documentation: [https://api.slack.com/methods/admin.teams.settings.setName](https://api.slack.com/methods/admin.teams.settings.setName)

```java
CompletableFuture<ApiResponse<DefaultSuccessTemplate>> adminTeamsSettingsSetNameAsync(
    final String token,
    final String teamId,
    final String name)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `token` | `String` | Header, Required | Authentication token. Requires scope: `admin.teams:write` |
| `teamId` | `String` | Form, Required | ID for the workspace to set the name for. |
| `name` | `String` | Form, Required | The new name of the workspace. |

## Requires scope

### slackAuth

`admin.teams:write`

## Response Type

This method returns an [`ApiResponse`](../../doc/api-response.md) instance. The `getResult()` getter of this instance returns the response data which is of type [`DefaultSuccessTemplate`](../../doc/models/default-success-template.md).

## Example Usage

```java
String token = "token6";
String teamId = "team_id6";
String name = "name0";

adminTeamsSettingsController.adminTeamsSettingsSetNameAsync(token, teamId, name).thenAccept(result -> {
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

