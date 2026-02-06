
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| environment | [`Environment`](../README.md#environments) | The API environment. <br> **Default: `Environment.PRODUCTION`** |
| httpClientConfig | [`Consumer<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Set up Http Client Configuration instance. |
| loggingConfig | [`Consumer<ApiLoggingConfiguration.Builder>`](../doc/api-logging-configuration-builder.md) | Set up Logging Configuration instance. |
| authorizationCodeAuth | [`AuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) | The Credentials Setter for OAuth 2 Authorization Code Grant |

The API client can be initialized as follows:

```java
import com.slack.Environment;
import com.slack.SlackWebApiClient;
import com.slack.authentication.AuthorizationCodeAuthModel;
import com.slack.exceptions.ApiException;
import com.slack.http.response.ApiResponse;
import com.slack.models.OauthScope;
import com.slack.models.OauthToken;
import java.io.IOException;
import java.util.Arrays;
import org.slf4j.event.Level;

public class Program {
    public static void main(String[] args) {
        SlackWebApiClient client = new SlackWebApiClient.Builder()
            .loggingConfig(builder -> builder
                    .level(Level.DEBUG)
                    .requestConfig(logConfigBuilder -> logConfigBuilder.body(true))
                    .responseConfig(logConfigBuilder -> logConfigBuilder.headers(true)))
            .httpClientConfig(configBuilder -> configBuilder
                    .timeout(0))
            .authorizationCodeAuth(new AuthorizationCodeAuthModel.Builder(
                    "OAuthClientId",
                    "OAuthClientSecret",
                    "OAuthRedirectUri"
                )
                .oauthScopes(Arrays.asList(
                        OauthScope.ADMIN,
                        OauthScope.ADMIN_APPSREAD
                    ))
                .build())
            .environment(Environment.PRODUCTION)
            .build();

    }
}
```

## Slack Web APIClient Class

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

### Controllers

| Name | Description | Return Type |
|  --- | --- | --- |
| `getAdminAppsController()` | Provides access to AdminApps controller. | `AdminAppsController` |
| `getAdminAppsApprovedController()` | Provides access to AdminAppsApproved controller. | `AdminAppsApprovedController` |
| `getAdminAppsRequestsController()` | Provides access to AdminAppsRequests controller. | `AdminAppsRequestsController` |
| `getAdminAppsRestrictedController()` | Provides access to AdminAppsRestricted controller. | `AdminAppsRestrictedController` |
| `getAdminConversationsController()` | Provides access to AdminConversations controller. | `AdminConversationsController` |
| `getAdminConversationsEkmController()` | Provides access to AdminConversationsEkm controller. | `AdminConversationsEkmController` |
| `getAdminConversationsRestrictAccessController()` | Provides access to AdminConversationsRestrictAccess controller. | `AdminConversationsRestrictAccessController` |
| `getAdminEmojiController()` | Provides access to AdminEmoji controller. | `AdminEmojiController` |
| `getAdminInviteRequestsController()` | Provides access to AdminInviteRequests controller. | `AdminInviteRequestsController` |
| `getAdminInviteRequestsApprovedController()` | Provides access to AdminInviteRequestsApproved controller. | `AdminInviteRequestsApprovedController` |
| `getAdminInviteRequestsDeniedController()` | Provides access to AdminInviteRequestsDenied controller. | `AdminInviteRequestsDeniedController` |
| `getAdminTeamsAdminsController()` | Provides access to AdminTeamsAdmins controller. | `AdminTeamsAdminsController` |
| `getAdminTeamsController()` | Provides access to AdminTeams controller. | `AdminTeamsController` |
| `getAdminTeamsOwnersController()` | Provides access to AdminTeamsOwners controller. | `AdminTeamsOwnersController` |
| `getAdminTeamsSettingsController()` | Provides access to AdminTeamsSettings controller. | `AdminTeamsSettingsController` |
| `getAdminUsergroupsController()` | Provides access to AdminUsergroups controller. | `AdminUsergroupsController` |
| `getAdminUsersController()` | Provides access to AdminUsers controller. | `AdminUsersController` |
| `getAdminUsersSessionController()` | Provides access to AdminUsersSession controller. | `AdminUsersSessionController` |
| `getApiController()` | Provides access to Api controller. | `ApiController` |
| `getAppsEventAuthorizationsController()` | Provides access to AppsEventAuthorizations controller. | `AppsEventAuthorizationsController` |
| `getAppsPermissionsController()` | Provides access to AppsPermissions controller. | `AppsPermissionsController` |
| `getAppsPermissionsResourcesController()` | Provides access to AppsPermissionsResources controller. | `AppsPermissionsResourcesController` |
| `getAppsPermissionsScopesController()` | Provides access to AppsPermissionsScopes controller. | `AppsPermissionsScopesController` |
| `getAppsPermissionsUsersController()` | Provides access to AppsPermissionsUsers controller. | `AppsPermissionsUsersController` |
| `getAppsController()` | Provides access to Apps controller. | `AppsController` |
| `getAuthController()` | Provides access to Auth controller. | `AuthController` |
| `getBotsController()` | Provides access to Bots controller. | `BotsController` |
| `getCallsController()` | Provides access to Calls controller. | `CallsController` |
| `getCallsParticipantsController()` | Provides access to CallsParticipants controller. | `CallsParticipantsController` |
| `getChatController()` | Provides access to Chat controller. | `ChatController` |
| `getChatScheduledMessagesController()` | Provides access to ChatScheduledMessages controller. | `ChatScheduledMessagesController` |
| `getConversationsController()` | Provides access to Conversations controller. | `ConversationsController` |
| `getDialogController()` | Provides access to Dialog controller. | `DialogController` |
| `getDndController()` | Provides access to Dnd controller. | `DndController` |
| `getEmojiController()` | Provides access to Emoji controller. | `EmojiController` |
| `getFilesCommentsController()` | Provides access to FilesComments controller. | `FilesCommentsController` |
| `getFilesController()` | Provides access to Files controller. | `FilesController` |
| `getFilesRemoteController()` | Provides access to FilesRemote controller. | `FilesRemoteController` |
| `getMigrationController()` | Provides access to Migration controller. | `MigrationController` |
| `getOauthController()` | Provides access to Oauth controller. | `OauthController` |
| `getOauthV2Controller()` | Provides access to OauthV2 controller. | `OauthV2Controller` |
| `getPinsController()` | Provides access to Pins controller. | `PinsController` |
| `getReactionsController()` | Provides access to Reactions controller. | `ReactionsController` |
| `getRemindersController()` | Provides access to Reminders controller. | `RemindersController` |
| `getRtmController()` | Provides access to Rtm controller. | `RtmController` |
| `getSearchController()` | Provides access to Search controller. | `SearchController` |
| `getStarsController()` | Provides access to Stars controller. | `StarsController` |
| `getTeamController()` | Provides access to Team controller. | `TeamController` |
| `getTeamProfileController()` | Provides access to TeamProfile controller. | `TeamProfileController` |
| `getUsergroupsController()` | Provides access to Usergroups controller. | `UsergroupsController` |
| `getUsergroupsUsersController()` | Provides access to UsergroupsUsers controller. | `UsergroupsUsersController` |
| `getUsersController()` | Provides access to Users controller. | `UsersController` |
| `getUsersProfileController()` | Provides access to UsersProfile controller. | `UsersProfileController` |
| `getViewsController()` | Provides access to Views controller. | `ViewsController` |
| `getWorkflowsController()` | Provides access to Workflows controller. | `WorkflowsController` |
| `getOauthAuthorizationController()` | Provides access to OauthAuthorization controller. | `OauthAuthorizationController` |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `shutdown()` | Shutdown the underlying HttpClient instance. | `void` |
| `getEnvironment()` | Current API environment. | `Environment` |
| `getHttpClient()` | The HTTP Client instance to use for making HTTP requests. | `HttpClient` |
| `getHttpClientConfig()` | Http Client Configuration instance. | [`ReadonlyHttpClientConfiguration`](../doc/http-client-configuration.md) |
| `getLoggingConfig()` | Logging Configuration instance. | [`ReadonlyLoggingConfiguration`](../doc/api-logging-configuration.md) |
| `getAuthorizationCodeAuth()` | The credentials to use with AuthorizationCodeAuth. | [`AuthorizationCodeAuth`](auth/oauth-2-authorization-code-grant.md) |
| `getBaseUri(Server server)` | Get base URI by current environment | `String` |
| `getBaseUri()` | Get base URI by current environment | `String` |

